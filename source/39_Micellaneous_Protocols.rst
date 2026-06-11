
.. _miscellaneous-protocols-micellaneous-protocols:

Miscellaneous Protocols
=======================


.. _efi-timestamp-protocol-micellaneous-protocols:

EFI Timestamp Protocol
----------------------


.. _efi-timestampprotocol-micellaneous-protocols:

EFI_TIMESTAMP_PROTOCOL
######################



**Summary**

The Timestamp protocol provides a platform independent interface for retrieving a high resolution timestamp counter.


**GUID**

.. code-block::

   #define EFI_TIMESTAMP_PROTOCOL_GUID \
     { 0xafbfde41, 0x2e6e, 0x4262,\
     { 0xba, 0x65, 0x62, 0xb9, 0x23, 0x6e, 0x54, 0x95 }}



**Protocol Interface Structure**

.. code-block::

   typedef struct _ EFI_TIMESTAMP_PROTOCOL {
     TIMESTAMP_GET                  GetTimestamp;
     TIMESTAMP_GET_PROPERTIES       GetProperties;
   }   EFI_TIMESTAMP_PROTOCOL;


.. _efi-timestamp-protocol-gettimestamp-micellaneous-protocols:

EFI_TIMESTAMP_PROTOCOL.GetTimestamp()
#####################################


**Summary**

Retrieves the current timestamp counter value.


**Prototype**

.. code-block::
  
   typedef  
   UINT64  
   (EFIAPI *TIMESTAMP_GET) (  
      VOID  
   );


**Description**

Retrieves the current value of a 64-bit free running timestamp counter. 

The counter shall count up in proportion to the amount of time that has passed. The counter value will always roll over to zero. The properties of the counter can be retrieved from GetProperties(). 

The caller should be prepared for the function to return the same value twice across successive calls. The counter value will not go backwards other than when wrapping, as defined by EndValue in GetProperties(). 

The frequency of the returned timestamp counter value must remain constant. Power management operations that affect clocking must not change the returned counter frequency. The quantization of counter value updates may vary as long as the value reflecting time passed remains consistent.



**Return Value**

The current value of the free running timestamp counter.


.. _efi-timestamp-protocol-getproperties-micellaneous-protocols:

EFI_TIMESTAMP_PROTOCOL.GetProperties()
######################################


**Summary**

Obtains timestamp counter properties including frequency and value limits.


**Prototype**

.. code-block::
  
   typedef  
   EFI_STATUS  
   (EFIAPI *TIMESTAMP_GET_PROPERTIES) (  
     OUT   EFI_TIMESTAMP_PROPERTIES      *Properties  
     );


**Parameters**

Properties
  The properties of the timestamp counter. See "Related Definitions" below.


**Description**

Retrieves the timestamp counter properties structure.

**Related Definitions**

.. code-block::

   typedef struct {
     UINT64          Frequency;
     
     UINT64          EndValue;
     } EFI_TIMESTAMP_PROPERTIES;
     

Frequency
  The frequency of the timestamp counter in Hz.

EndValue
  The value that the timestamp counter ends with immediately before it rolls over. For example, a 64-bit free running counter would have an EndValue of 0xFFFFFFFFFFFFFFFF. A 24-bit free running counter would have an EndValue of 0xFFFFFF.


**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - The properties were successfully retrieved.
   * - EFI_DEVICE_ERROR
     - An error occurred trying to retrieve the properties of the timestamp counter subsystem. *Properties* is not updated.
   * - EFI_INVALID_PARAMETER
     - *Properties* is **NULL**.



.. _reset-notification-protocol_micellaneous_protocols:

Reset Notification Protocol
---------------------------


.. _efi-reset-notification-protocol-micellaneous-protocols:

EFI_RESET_NOTIFICATION_PROTOCOL
###############################


**Summary**

This protocol provides services to register for a notification when ResetSystem is called.


**GUID**

.. code-block::

   #define EFI_RESET_NOTIFICATION_PROTOCOL_GUID \
     { 0x9da34ae0, 0xeaf9, 0x4bbf, \
     { 0x8e, 0xc3, 0xfd, 0x60, 0x22, 0x6c, 0x44, 0xbe } }


**Protocol Interface Structure**

.. code-block::

   typedef struct _EFI_RESET_NOTIFICATION_PROTOCOL {
     EFI_REGISTER_RESET_NOTIFY               RegisterResetNotify;
     EFI_UNREGISTER_RESET_NOTIFY             UnRegisterResetNotify;
   }   EFI_RESET_NOTIFICATION_PROTOCOL;


**Parameters**

RegisterResetNotify
  Register a notification function to be called when ResetSystem() is called.

UnRegisterResetNotify
  Removes a reset notification function that has been previously registered with RegisterResetNotify().


.. _efi-reset-notification-protocol-registerresetnotify-micellaneous-protocols:


EFI_RESET_NOTIFICATION_PROTOCOL.RegisterResetNotify()
#####################################################


**Summary**

Register a notification function to be called when ResetSystem() is called.


**Prototype**

.. code-block::
  
   typedef  
   EFI_STATUS  
   (EFIAPI *EFI_REGISTER_RESET_NOTIFY) (  
     IN EFI_RESET_NOTIFICATION_PROTOCOL         *This,  
     IN EFI_RESET_SYSTEM                        *ResetFunction,  
   );
  

**Parameters**

This
  A pointer to the :ref:`efi-reset-notification-protocol-micellaneous-protocols`  instance.

ResetFunction
  Points to the function to be called when a :ref:`resetsystem` is executed.


**Description**

The *RegisterResetNotify()* function registers a notification function that is called when *ResetSystem()* is called and prior to completing the reset of the platform. 

The registered functions must not perform a platform reset themselves. These notifications are intended only for the notification of components which may need some special-purpose maintenance prior to the platform resetting. 

The list of registered reset notification functions are processed if *ResetSystem()* is called before *ExitBootServices()* . The list of registered reset notification functions is ignored if *ResetSystem()* is called after *ExitBootServices()* .


**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - The reset notification function was successfully registered.
   * - EFI_INVALID_PARAMETER
     - ResetFunction is **NULL**.
   * - EFI_OUT_OF_RESOURCES
     - There are not enough resources available to register the reset notification function.
   * - EFI_ALREADY_STARTED
     - The reset notification function specified by ResetFunction has already been registered.


.. _efi_reset_notification_protocol.unregisterresetnotify_micellaneous_protocols:

EFI_RESET_NOTIFICATION_PROTOCOL.UnregisterResetNotify()
#######################################################


**Summary**

Unregister a notification function.


**Prototype**

.. code-block::
  
   typedef
   EFI_STATUS
   (EFIAPI *EFI_UNREGISTER_RESET_NOTIFY) (
     IN EFI_RESET_NOTIFICATION_PROTOCOL      *This,
     IN EFI_RESET_SYSTEM                     *ResetFunction
   );


**Parameters**

This
  A pointer to the EFI_RESET_NOTIFICATION_PROTOCOL instance. 

ResetFunction
  The pointer to the ResetFunction being unregistered. 


**Description**

The UnregisterResetNotify() function removes the previously registered notification using RegisterResetNotify().   


**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - The reset notification function was unregistered.
   * - EFI_INVALID_PARAMETER
     - ResetFunction is **NULL**.
   * - EFI_INVALID_PARAMETER
     - The reset notification function specified by ResetFunction was not previously registered using RegisterResetNotify().
