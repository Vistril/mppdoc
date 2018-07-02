# Multiplayer Piano API Documentation
work in progress; [edits welcome](https://github.com/ledlamp/mppdoc/edit/master/api.md)

## Table of Contents
- [MPP.press(id, vol)                                    ](#mpppressid-vol)
- [MPP.release(id)                                       ](#mppreleaseid)
- [MPP.piano                                             ](#mpppiano)
  - [MPP.piano.audio                                     ](#mpppianoaudio)
    - [MPP.piano.audio.context                           ](#mpppianoaudiocontext)
    - [MPP.piano.audio.limiterNode                       ](#mpppianoaudiolimiternode)
    - [MPP.piano.audio.paused                            ](#mpppianoaudiopaused)
    - [MPP.piano.audio.pianoGain                         ](#mpppianoaudiopianogain)
    - [MPP.piano.audio.playings                          ](#mpppianoaudioplayings)
    - [MPP.piano.audio.sounds                            ](#mpppianoaudiosounds)
    - [MPP.piano.audio.synthGain                         ](#mpppianoaudiosynthgain)
    - [MPP.piano.audio.threshold                         ](#mpppianoaudiothreshold)
    - [MPP.piano.audio.volume                            ](#mpppianoaudiovolume)
    - [MPP.piano.audio.worker                            ](#mpppianoaudioworker)
    - [MPP.piano.audio.actualPlay(id, vol, time, part_id)](#mpppianoaudioactualplayid-vol-time-part_id)
    - [MPP.piano.audio.actualStop(id, time, part_id)     ](#mpppianoaudioactualstopid-time-part_id)
    - [MPP.piano.audio.init(cb)                          ](#mpppianoaudioinitcb)
    - [MPP.piano.audio.load(id, url, cb)                 ](#mpppianoaudioloadid-url-cb)
    - [MPP.piano.audio.play(id, vol, delay_ms, part_id)  ](#mpppianoaudioplayid-vol-delay_ms-part_id)
    - [MPP.piano.audio.resume()                          ](#mpppianoaudioresume)
    - [MPP.piano.audio.setVolume(vol)                    ](#mpppianoaudiosetvolumevol)
    - [MPP.piano.audio.stop(id, delay_ms, part_id)       ](#mpppianoaudiostopid-delay_ms-part_id)
  - [MPP.piano.play(id, vol, delay_ms, part_id)          ](#mpppianoplayid-vol-delay_ms-part_id)
  - [MPP.piano.stop(note, participant, delay_ms)         ](#mpppianostopnote-participant-delay_ms)
  - [MPP.piano.keys                                      ](#mpppianokeys)
  - [MPP.piano.renderer                                  ](#mpppianorenderer)
    - [MPP.piano.renderer.blackBlipHeight                ](#mpppianorendererblackblipheight)
    - [MPP.piano.renderer.blackBlipWidth                 ](#mpppianorendererblackblipwidth)
    - [MPP.piano.renderer.blackBlipX                     ](#mpppianorendererblackblipx)
    - [MPP.piano.renderer.blackBlipY                     ](#mpppianorendererblackblipy)
    - [MPP.piano.renderer.blackKeyHeight                 ](#mpppianorendererblackkeyheight)
    - [MPP.piano.renderer.blackKeyOffset                 ](#mpppianorendererblackkeyoffset)
    - [MPP.piano.renderer.blackKeyRender                 ](#mpppianorendererblackkeyrender)
    - [MPP.piano.renderer.blackKeyWidth                  ](#mpppianorendererblackkeywidth)
    - [MPP.piano.renderer.canvas                         ](#mpppianorenderercanvas)
    - [MPP.piano.renderer.ctx                            ](#mpppianorendererctx)
    - [MPP.piano.renderer.height                         ](#mpppianorendererheight)
    - [MPP.piano.renderer.keyMovement                    ](#mpppianorendererkeymovement)
    - [MPP.piano.renderer.piano                          ](#mpppianorendererpiano)
    - [MPP.piano.renderer.shadowRender                   ](#mpppianorenderershadowrender)
    - [MPP.piano.renderer.whiteBlipHeight                ](#mpppianorendererwhiteblipheight)
    - [MPP.piano.renderer.whiteBlipWidth                 ](#mpppianorendererwhiteblipwidth)
    - [MPP.piano.renderer.whiteBlipX                     ](#mpppianorendererwhiteblipx)
    - [MPP.piano.renderer.whiteBlipY                     ](#mpppianorendererwhiteblipy)
    - [MPP.piano.renderer.whiteKeyHeight                 ](#mpppianorendererwhitekeyheight)
    - [MPP.piano.renderer.whiteKeyRender                 ](#mpppianorendererwhitekeyrender)
    - [MPP.piano.renderer.whiteKeyWidth                  ](#mpppianorendererwhitekeywidth)
    - [MPP.piano.renderer.width                          ](#mpppianorendererwidth)
    - [MPP.piano.renderer.getHit(x, y)                   ](#mpppianorenderergethitx-y)
    - [MPP.piano.renderer.init(piano)                    ](#mpppianorendererinitpiano)
    - [MPP.piano.renderer.redraw()                       ](#mpppianorendererredraw)
    - [MPP.piano.renderer.resize(width, height)          ](#mpppianorendererresizewidth-height)
    - [MPP.piano.renderer.visualize(key, color)          ](#mpppianorenderervisualizekey-color)
  - [MPP.piano.rootElement                               ](#mpppianorootelement)
- [MPP.client                                            ](#mppclient)
  - [MPP.client.canConnect                               ](#mppclientcanconnect)
  - [MPP.client.channel                                  ](#mppclientchannel)
  - [MPP.client.connectionAttempts                       ](#mppclientconnectionattempts)
  - [MPP.client.connectionTime                           ](#mppclientconnectiontime)
  - [MPP.client.desiredChannelId                         ](#mppclientdesiredchannelid)
  - [MPP.client.desiredChannelSettings                   ](#mppclientdesiredchannelsettings)
  - [MPP.client.noteBuffer                               ](#mppclientnotebuffer)
  - [MPP.client.noteBufferTime                           ](#mppclientnotebuffertime)
  - [MPP.client.noteFlushInterval                        ](#mppclientnoteflushinterval)
  - [MPP.client.participantId                            ](#mppclientparticipantid)
  - [MPP.client.pingInterval                             ](#mppclientpinginterval)
  - [MPP.client.ppl                                      ](#mppclientppl)
  - [MPP.client.serverTimeOffset                         ](#mppclientservertimeoffset)
  - [MPP.client.uri                                      ](#mppclienturi)
  - [MPP.client.user                                     ](#mppclientuser)
  - [MPP.client.ws                                       ](#mppclientws)
  - [MPP.client.bindEventListeners()                     ](#mppclientbindeventlisteners)
  - [MPP.client.connect()                                ](#mppclientconnect)
  - [MPP.client.countParticipants()                      ](#mppclientcountparticipants)
  - [MPP.client.emit(evtn)                               ](#mppclientemitevtn)
  - [MPP.client.findParticipantById(id)                  ](#mppclientfindparticipantbyidid)
  - [MPP.client.getChannelSetting(key)                   ](#mppclientgetchannelsettingkey)
  - [MPP.client.getOwnParticipant()                      ](#mppclientgetownparticipant)
  - [MPP.client.isConnected()                            ](#mppclientisconnected)
  - [MPP.client.isConnecting()                           ](#mppclientisconnecting)
  - [MPP.client.isOwner()                                ](#mppclientisowner)
  - [MPP.client.isSupported()                            ](#mppclientissupported)
  - [MPP.client.off(evnt, fn)                            ](#mppclientoffevnt-fn)
  - [MPP.client.offlineChannelSettings                   ](#mppclientofflinechannelsettings)
  - [MPP.client.offlineParticipant                       ](#mppclientofflineparticipant)
  - [MPP.client.on(evtn, fn)                             ](#mppclientonevtn-fn)
  - [MPP.client.participantUpdate(update)                ](#mppclientparticipantupdateupdate)
  - [MPP.client.preventsPlaying                          ](#mppclientpreventsplaying)
  - [MPP.client.receiveServerTime(time, echo)            ](#mppclientreceiveservertimetime-echo)
  - [MPP.client.send(raw)                                ](#mppclientsendraw)
  - [MPP.client.sendArray(arr)                           ](#mppclientsendarrayarr)
  - [MPP.client.setChannel(id, [set])                    ](#mppclientsetchannelid-set)
  - [MPP.client.setParticipants(ppl)                     ](#mppclientsetparticipantsppl)
  - [MPP.client.start()                                  ](#mppclientstart)
  - [MPP.client.startNote(note, [vel])                   ](#mppclientstartnotenote-vel)
  - [MPP.client.stop()                                   ](#mppclientstop)
  - [MPP.client.stopNote(note)                           ](#mppclientstopnotenote)
  - [event: "a"                                          ](#mppclient-event-a)
  - [event: "bye"                                        ](#mppclient-event-bye)
  - [event: "c"                                          ](#mppclient-event-c)
  - [event: "ch"                                         ](#mppclient-event-ch)
  - [event: "connect"                                    ](#mppclient-event-connect)
  - [event: "count"                                      ](#mppclient-event-count)
  - [event: "disconnect"                                 ](#mppclient-event-disconnect)
  - [event: "hi"                                         ](#mppclient-event-hi)
  - [event: "ls"                                         ](#mppclient-event-ls)
  - [event: "m"                                          ](#mppclient-event-m)
  - [event: "n"                                          ](#mppclient-event-n)
  - [event: "notification"                               ](#mppclient-event-notification)
  - [event: "nq"                                         ](#mppclient-event-nq)
  - [event: "p"                                          ](#mppclient-event-p)
  - [event: "participant added"                          ](#mppclient-event-participant-added)
  - [event: "participant removed"                        ](#mppclient-event-participant-removed)
  - [event: "participant update"                         ](#mppclient-event-participant-update)
  - [event: "status"                                     ](#mppclient-event-status)
  - [event: "t"                                          ](#mppclient-event-t)
- [MPP.chat                                              ](#mppchat)
  - [MPP.chat.blur()                                     ](#mppchatblur)
  - [MPP.chat.clear()                                    ](#mppchatclear)
  - [MPP.chat.hide()                                     ](#mppchathide)
  - [MPP.chat.receive(msg)                               ](#mppchatreceivemsg)
  - [MPP.chat.scrollToBottom()                           ](#mppchatscrolltobottom)
  - [MPP.chat.send(message)                              ](#mppchatsendmessage)
  - [MPP.chat.show()                                     ](#mppchatshow)
- [MPP.noteQuota                                         ](#mppnotequota)
  - [MPP.noteQuota.allowance                             ](#mppnotequotaallowance)
  - [MPP.noteQuota.cb(points)                            ](#mppnotequotacbpoints)
  - [MPP.noteQuota.histLen                               ](#mppnotequotahistlen)
  - [MPP.noteQuota.history                               ](#mppnotequotahistory)
  - [MPP.noteQuota.max                                   ](#mppnotequotamax)
  - [MPP.noteQuota.points                                ](#mppnotequotapoints)
  - [MPP.noteQuota.getParams()                           ](#mppnotequotagetparams)
  - [MPP.noteQuota.resetPoints()                         ](#mppnotequotaresetpoints)
  - [MPP.noteQuota.setParams(params)                     ](#mppnotequotasetparamsparams)
  - [MPP.noteQuota.spend(needed)                         ](#mppnotequotaspendneeded)
  - [MPP.noteQuota.tick()                                ](#mppnotequotatick)
- [MPP.soundSelector                                     ](#mppsoundselector)
  - [MPP.soundSelector.initialized                       ](#mppsoundselectorinitialized)
  - [MPP.soundSelector.keys                              ](#mppsoundselectorkeys)
  - [MPP.soundSelector.loading                           ](#mppsoundselectorloading)
  - [MPP.soundSelector.packs                             ](#mppsoundselectorpacks)
  - [MPP.soundSelector.piano                             ](#mppsoundselectorpiano)
  - [MPP.soundSelector.soundSelection                    ](#mppsoundselectorsoundselection)
  - [MPP.soundSelector.addPack(pack, load)               ](#mppsoundselectoraddpackpack-load)
  - [MPP.soundSelector.addPacks(packs)                   ](#mppsoundselectoraddpackspacks)
  - [MPP.soundSelector.init()                            ](#mppsoundselectorinit)
  - [MPP.soundSelector.loadPack(pack, f)                 ](#mppsoundselectorloadpackpack-f)
  - [MPP.soundSelector.removePack(name)                  ](#mppsoundselectorremovepackname)



### MPP.press(id, vol)
- `id` <[String]> the id of the key, such as `a1`
- `vol` <[Number]> velocity of the key press; ranges from 0-1

Presses a key as the user, consuming note quota and sending it to other participants.


### MPP.release(id)
- `id` <[String]> the id of the key, such as `a1`

Releases a key pressed by MPP.press


### MPP.piano
- type: <[Piano](http://www.multiplayerpiano.com/script.js)>


### MPP.piano.audio
### MPP.piano.audio.context
### MPP.piano.audio.limiterNode
### MPP.piano.audio.paused
### MPP.piano.audio.pianoGain
### MPP.piano.audio.playings
### MPP.piano.audio.sounds
### MPP.piano.audio.synthGain
### MPP.piano.audio.threshold
### MPP.piano.audio.volume
### MPP.piano.audio.worker
### MPP.piano.audio.actualPlay(id, vol, time, part_id)
### MPP.piano.audio.actualStop(id, time, part_id)
### MPP.piano.audio.init(cb)
### MPP.piano.audio.load(id, url, cb)
### MPP.piano.audio.play(id, vol, delay_ms, part_id)
### MPP.piano.audio.resume()
### MPP.piano.audio.setVolume(vol)
### MPP.piano.audio.stop(id, delay_ms, part_id)
### MPP.piano.play(id, vol, delay_ms, part_id)
### MPP.piano.stop(note, participant, delay_ms)
### MPP.piano.keys
### MPP.piano.renderer
### MPP.piano.renderer.blackBlipHeight
### MPP.piano.renderer.blackBlipWidth
### MPP.piano.renderer.blackBlipX
### MPP.piano.renderer.blackBlipY
### MPP.piano.renderer.blackKeyHeight
### MPP.piano.renderer.blackKeyOffset
### MPP.piano.renderer.blackKeyRender
### MPP.piano.renderer.blackKeyWidth
### MPP.piano.renderer.canvas
### MPP.piano.renderer.ctx
### MPP.piano.renderer.height
### MPP.piano.renderer.keyMovement
### MPP.piano.renderer.piano
### MPP.piano.renderer.shadowRender
### MPP.piano.renderer.whiteBlipHeight
### MPP.piano.renderer.whiteBlipWidth
### MPP.piano.renderer.whiteBlipX
### MPP.piano.renderer.whiteBlipY
### MPP.piano.renderer.whiteKeyHeight
### MPP.piano.renderer.whiteKeyRender
### MPP.piano.renderer.whiteKeyWidth
### MPP.piano.renderer.width
### MPP.piano.renderer.getHit(x, y)
### MPP.piano.renderer.init(piano)
### MPP.piano.renderer.redraw()
### MPP.piano.renderer.resize(width, height)
### MPP.piano.renderer.visualize(key, color)
### MPP.piano.rootElement


### MPP.client
- type: <[Client](http://www.multiplayerpiano.com/Client.js)>


### MPP.client.canConnect
- type: <[Boolean]>

The client will not connect if this is set to `false`.


### MPP.client.channel
- type: <[Object]>
  
Represents the channel (room) the client is in.


### MPP.client.connectionAttempts
- type: <[Number]>
  
Number of times the client tried to reconnect after a connection failure.


### MPP.client.connectionTime
- type: <[Number]>

The time the current connection was made, in UNIX time. This will be undefined if the client is not connected.


### MPP.client.desiredChannelId
- type: <[String]>
 
The name of the channel (room) the client wants to be connected to.


### MPP.client.desiredChannelSettings
- type: <[Object]>
  
Like MPP.client.desiredChannelId, the settings for the channel (room) the client wants to connect to, if it is going to be a new channel.


### MPP.client.noteBuffer
- type: <[Array]>
  
Buffer of note messages to be sent to the server. This buffer is sent to the server & cleared every 200 ms by MPP.client.noteFlushInterval
.


### MPP.client.noteBufferTime
- type: <[Number]>
  
This will be the UNIX time of the first note message in the note buffer. It is used to calculate the difference in ms between that first note and each note added to the buffer.


### MPP.client.noteFlushInterval
- type: <[Number]>
  
ID of the interval used to dispatch the note buffer. Used with clearInterval() when the client is disconnected.


### MPP.client.participantId
- type: <[String]>
  
The client's participant ID.


### MPP.client.pingInterval
- type: <[Number]>

ID of the interval used to send a ping message to the server.


### MPP.client.ppl
- type: <[Object]>
  
This contains all participant objects that the client knows, mapped by their participant ID.


### MPP.client.serverTimeOffset
- type: <[Number]>

Used to correct any offset of the server's time versus the client's time. This ensures notes are always played at their timing target (1 second after it was really played). It's also used to ensure accuracy of crown pick-up timing.


### MPP.client.uri
- type: <[String]>
  
Websocket server URL for the client to connect to.


### MPP.client.user
- type: <[Object]>

Represents the client's user. This is set by the server via the "u" event.


### MPP.client.ws
- type: <[WebSocket]>

The client's current WebSocket instance. Note that this is re-created every time the client connects, because WebSockets are basically one-time-use connections.


### MPP.client.bindEventListeners()

Initializes internal event listeners. Used on connect.


### MPP.client.connect()

Connects the client if possible, that is, if MPP.client.canConnect & MPP.client.isSupported() are true, and MPP.client.isConnected() & MPP.client.isConnecting() are false.


### MPP.client.countParticipants()
- returns: <[Number]> the number of participants online, or the number of objects in MPP.client.ppl.


### MPP.client.emit(evtn, [args…])
- `evtn` <[String]> name of the event.
- `args…` <[any]> arguments to pass to the event listeners.

Emits an event, which will call all listeners on the given event.


### MPP.client.findParticipantById(id)
- `id` <[String]> ID of the participant to find
- returns: <[Object]> The participant


### MPP.client.getChannelSetting(key)
- `key` <[String]>
- returns: <[Any]>

Returns a setting's value whose name is the given key (i.e. `crownsolo`). Depending on whether the client is connected, this value will come from MPP.client.channel.settings or MPP.client.offlineChannelSettings.


### MPP.client.getOwnParticipant()
- returns: <[Object]> The client's own participant object.


### MPP.client.isConnected()
- returns: <[Boolean]> Whether the client is connected.


### MPP.client.isConnecting()
- returns: <[Boolean]> Whether the client is in the process of connecting.


### MPP.client.isOwner()
- returns: <[Boolean]> Whether the client is the owner of its channel.


### MPP.client.isSupported()
- returns: <[Boolean]> Whether the client is supported on the platform.
  
This is true if `WebSocket` exists as a Function.


### MPP.client.off(evnt, fn)
- `evnt` <[String]> Event name.
- `fn` <[Function]> The listener function to remove.
  
Removes an event listener function.


### MPP.client.offlineChannelSettings
- type: <[Object]>
  
The settings to use for the channel when the client is not connected.


### MPP.client.offlineParticipant
- type: <[Object]>
  
The participant to use when the client is not connected.


### MPP.client.on(evtn, fn)
- `evnt` <[String]> Event name
- `fn` <[Function]> Event listener functon
  
Registers the function as an event listener for the given event. Example:
```js
MPP.client.on("meow", function(message){
    console.log("A cat has meowed the following message:" + message);
});

MPP.client.emit("meow", "🅱istril ghey");
```


### MPP.client.participantUpdate(update)
- `update` <[Object]> Updated participant

Used internally to update participants in MPP.client.ppl.


### MPP.client.preventsPlaying()
- returns: <[Boolean]> If `true`, the client is not permitted to play (such as in "Only owner can play" rooms).


### MPP.client.receiveServerTime(time, echo)
- `time` <[Number]> Server's UNIX time
- `echo` <[Number]> idk what this is but it doesn't appear to be used

Used internally to configure MPP.client.serverTimeOffset based on the server's time broadcasted via "t" and "hi" events.


### MPP.client.send(raw)
- `raw` <[String]> Message

Sends a raw string through the WebSocket.


### MPP.client.sendArray(arr)
- `arr` <[Array]> Array of messages to send to the server

Serializes and sends the array of messages to the server. Each message is an Object whose "m" property is the event name it represents.


### MPP.client.setChannel(id, [set])
- `id` <[String]> Name of the channel (room) to join
- `set` <[Object]> Channel settings, if creating a new room

Sets MPP.client.desiredChannelId and MPP.client.desiredChannelSettings to `id` and `set`, respectively, and sends a "ch" to the server if the client is connected.


### MPP.client.setParticipants(ppl)
- `ppl` <[Object]>

Sets MPP.client.ppl by removing those who aren't in `ppl` and leaving those who are; then updating each one.


### MPP.client.start()

Enables the client to connect and connects it.


### MPP.client.startNote(note, [vel])
- `note` <[String]> Name of the note, i.e. `c7`
- `vel`, <[Number]> Velocity of the note

Sends a note press to the server.


### MPP.client.stop()

Sets MPP.client.canConnect to false and closes the WebSocket.


### MPP.client.stopNote(note)
- `note` <[String]> Name of the note

Sends a note release to the server.


### MPP.client event: "a"
- `msg` <[Object]> A chat message
  - `msg.a` <[String]> The message content
  - `msg.t` <[Number]> Time the message was received by the server (?)
  - `msg.p` <[Object]> The participant who sent the message
    `msg.p_id` <[String]> User id of the participant
    `msg.p.name` <[String]> Name of the participant
    `msg.p.color` <[String]> The participant's color, in hex
    `msg.p.id` <[String]> The participant's id
    
Note that when sending a chat message, you create a msg with your message content in `message`.


### MPP.client event: "bye"
- `msg` <[Object]>
  - `msg.p` <[String]> Participant Id

Emitted when a participant leaves; used to remove participants from MPP.client.ppl.


### MPP.client event: "c"
- `msg` <[Object]>
  - `msg.c` <[Array]> Array of chat messages (like those in "a")

Used to load the chat history when you join a channel.


### MPP.client event: "ch"
- `msg` <[Object]>
  - `msg.ch` <[Object]>
    - `msg.ch._id` <[String]> Name of the channel
    - `msg.ch.settings` <[Object]> Settings of the channel
    - `msg.ch.count` <[Number]> Number of participants in the channel
  - `msg.p` <[String]> Your participant id
  - `msg.ppl` <[Array]> Array of all the participants in the channel.
  
This event is emitted whenever the channel is changed.


### MPP.client event: "connect"

Emmitted when the WebSocket opens.


### MPP.client event: "count"
- <[Number]> Number of participants

This is emitted every time the number of participants changes.


### MPP.client event: "disconnect"

Emitted when the WebSocket closes.

### MPP.client event: "hi"
- `msg` <[Object]>
  - `msg.motd` <[String]> The message of the day.
  - `msg.t` <[Number]> The server's UNIX time.
  - `msg.u` <[Object]> The user that the client will be known as.
  - `msg.v` <[String]> MPP Version

Emitted by the server once the connection is successful and the client is ready to send messages.


### MPP.client event: "ls"


### MPP.client event: "m"
### MPP.client event: "n"
### MPP.client event: "notification"
### MPP.client event: "nq"
### MPP.client event: "p"
### MPP.client event: "participant added"
### MPP.client event: "participant removed"
### MPP.client event: "participant update"
### MPP.client event: "status"
### MPP.client event: "t"
### MPP.chat
### MPP.chat.blur()
### MPP.chat.clear()
### MPP.chat.hide()
### MPP.chat.receive(msg)
### MPP.chat.scrollToBottom()
### MPP.chat.send(message)
### MPP.chat.show()
### MPP.noteQuota
### MPP.noteQuota.allowance
### MPP.noteQuota.cb(points)
### MPP.noteQuota.histLen
### MPP.noteQuota.history
### MPP.noteQuota.max
### MPP.noteQuota.points
### MPP.noteQuota.getParams()
### MPP.noteQuota.resetPoints()
### MPP.noteQuota.setParams(params)
### MPP.noteQuota.spend(needed)
### MPP.noteQuota.tick()
### MPP.soundSelector
### MPP.soundSelector.initialized
### MPP.soundSelector.keys
### MPP.soundSelector.loading
### MPP.soundSelector.packs
### MPP.soundSelector.piano
### MPP.soundSelector.soundSelection
### MPP.soundSelector.addPack(pack, load)
### MPP.soundSelector.addPacks(packs)
### MPP.soundSelector.init()
### MPP.soundSelector.loadPack(pack, f)
### MPP.soundSelector.removePack(name)
