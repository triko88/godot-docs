.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the WebSocketMultiplayerPeer.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_WebSocketMultiplayerPeer:

WebSocketMultiplayerPeer
========================

**Inherits:** :ref:`NetworkedMultiplayerPeer<class_NetworkedMultiplayerPeer>` **<** :ref:`PacketPeer<class_PacketPeer>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`WebSocketClient<class_WebSocketClient>`, :ref:`WebSocketServer<class_WebSocketServer>`

**Category:** Core

Brief Description
-----------------

Base class for WebSocket server and client.

Methods
-------

+-------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`WebSocketPeer<class_WebSocketPeer>` | :ref:`get_peer<class_WebSocketMultiplayerPeer_method_get_peer>` **(** :ref:`int<class_int>` peer_id **)** const                                                                                                                                              |
+-------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>`     | :ref:`set_buffers<class_WebSocketMultiplayerPeer_method_set_buffers>` **(** :ref:`int<class_int>` input_buffer_size_kb, :ref:`int<class_int>` input_max_packets, :ref:`int<class_int>` output_buffer_size_kb, :ref:`int<class_int>` output_max_packets **)** |
+-------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Signals
-------

.. _class_WebSocketMultiplayerPeer_signal_peer_packet:

- **peer_packet** **(** :ref:`int<class_int>` peer_source **)**

Emitted when a packet is received from a peer. Note: this signal is only emitted when the client or server is configured to use Godot multiplayer API.

Description
-----------

Base class for WebSocket server and client, allowing them to be used as network peer for the :ref:`MultiplayerAPI<class_MultiplayerAPI>`.

Method Descriptions
-------------------

.. _class_WebSocketMultiplayerPeer_method_get_peer:

- :ref:`WebSocketPeer<class_WebSocketPeer>` **get_peer** **(** :ref:`int<class_int>` peer_id **)** const

Returns the :ref:`WebSocketPeer<class_WebSocketPeer>` associated to the given ``peer_id``.

.. _class_WebSocketMultiplayerPeer_method_set_buffers:

- :ref:`Error<enum_@GlobalScope_Error>` **set_buffers** **(** :ref:`int<class_int>` input_buffer_size_kb, :ref:`int<class_int>` input_max_packets, :ref:`int<class_int>` output_buffer_size_kb, :ref:`int<class_int>` output_max_packets **)**

Configure the buffers sizes for this WebSocket peer. Default values can be specified in project settings under ``network/limits``. For server, values are meant per connected peer.

The first two parameters define the size and queued packets limits of the input buffer, the last two of the output buffer.

Buffer sizes are expressed in KiB, so ``4 = 2^12 = 4096 bytes``. All parameters will be rounded up to the nearest power of two.

NOTE: HTML5 exports only use the input buffer since the output one is managed by browsers.

