# Multiplayer Piano API Documentation

## Table of Contents
- [MPP.press(id, vol)                                    ](mpppressid-vol)
- [MPP.release(id)                                       ](mppreleaseid)
- [MPP.piano                                             ](mpppiano)
  - [MPP.piano.audio                                     ](mpppianoaudio)
    - [MPP.piano.audio.context                           ](mpppianoaudiocontext)
    - [MPP.piano.audio.limiterNode                       ](mpppianoaudiolimiternode)
    - [MPP.piano.audio.paused                            ](mpppianoaudiopaused)
    - [MPP.piano.audio.pianoGain                         ](mpppianoaudiopianogain)
    - [MPP.piano.audio.playings                          ](mpppianoaudioplayings)
    - [MPP.piano.audio.sounds                            ](mpppianoaudiosounds)
    - [MPP.piano.audio.synthGain                         ](mpppianoaudiosynthgain)
    - [MPP.piano.audio.threshold                         ](mpppianoaudiothreshold)
    - [MPP.piano.audio.volume                            ](mpppianoaudiovolume)
    - [MPP.piano.audio.worker                            ](mpppianoaudioworker)
    - [MPP.piano.audio.actualPlay(id, vol, time, part_id)](mpppianoaudioactualplayid-vol-time-part_id)
    - [MPP.piano.audio.actualStop(id, time, part_id)     ](mpppianoaudioactualstopid-time-part_id)
    - [MPP.piano.audio.init(cb)                          ](mpppianoaudioinitcb)
    - [MPP.piano.audio.load(id, url, cb)                 ](mpppianoaudioloadid-url-cb)
    - [MPP.piano.audio.play(id, vol, delay_ms, part_id)  ](mpppianoaudioplayid-vol-delay_ms-part_id)
    - [MPP.piano.audio.resume()                          ](mpppianoaudioresume)
    - [MPP.piano.audio.setVolume(vol)                    ](mpppianoaudiosetvolumevol)
    - [MPP.piano.audio.stop(id, delay_ms, part_id)       ](mpppianoaudiostopid-delay_ms-part_id)
  - [MPP.piano.play(id, vol, delay_ms, part_id)          ](mpppianoplayid-vol-delay_ms-part_id)
  - [MPP.piano.stop(note, participant, delay_ms)         ](mpppianostopnote-participant-delay_ms)
  - [MPP.piano.keys                                      ](mpppianokeys)
  - [MPP.piano.renderer                                  ](mpppianorenderer)
    - [MPP.piano.renderer.blackBlipHeight                ](mpppianorendererblackblipheight)
    - [MPP.piano.renderer.blackBlipWidth                 ](mpppianorendererblackblipwidth)
    - [MPP.piano.renderer.blackBlipX                     ](mpppianorendererblackblipx)
    - [MPP.piano.renderer.blackBlipY                     ](mpppianorendererblackblipy)
    - [MPP.piano.renderer.blackKeyHeight                 ](mpppianorendererblackkeyheight)
    - [MPP.piano.renderer.blackKeyOffset                 ](mpppianorendererblackkeyoffset)
    - [MPP.piano.renderer.blackKeyRender                 ](mpppianorendererblackkeyrender)
    - [MPP.piano.renderer.blackKeyWidth                  ](mpppianorendererblackkeywidth)
    - [MPP.piano.renderer.canvas                         ](mpppianorenderercanvas)
    - [MPP.piano.renderer.ctx                            ](mpppianorendererctx)
    - [MPP.piano.renderer.height                         ](mpppianorendererheight)
    - [MPP.piano.renderer.keyMovement                    ](mpppianorendererkeymovement)
    - [MPP.piano.renderer.piano                          ](mpppianorendererpiano)
    - [MPP.piano.renderer.shadowRender                   ](mpppianorenderershadowrender)
    - [MPP.piano.renderer.whiteBlipHeight                ](mpppianorendererwhiteblipheight)
    - [MPP.piano.renderer.whiteBlipWidth                 ](mpppianorendererwhiteblipwidth)
    - [MPP.piano.renderer.whiteBlipX                     ](mpppianorendererwhiteblipx)
    - [MPP.piano.renderer.whiteBlipY                     ](mpppianorendererwhiteblipy)
    - [MPP.piano.renderer.whiteKeyHeight                 ](mpppianorendererwhitekeyheight)
    - [MPP.piano.renderer.whiteKeyRender                 ](mpppianorendererwhitekeyrender)
    - [MPP.piano.renderer.whiteKeyWidth                  ](mpppianorendererwhitekeywidth)
    - [MPP.piano.renderer.width                          ](mpppianorendererwidth)
    - [MPP.piano.renderer.getHit(x, y)                   ](mpppianorenderergethitx-y)
    - [MPP.piano.renderer.init(piano)                    ](mpppianorendererinitpiano)
    - [MPP.piano.renderer.redraw()                       ](mpppianorendererredraw)
    - [MPP.piano.renderer.resize(width, height)          ](mpppianorendererresizewidth-height)
    - [MPP.piano.renderer.visualize(key, color)          ](mpppianorenderervisualizekey-color)
  - [MPP.piano.rootElement                               ](mpppianorootelement)
- [MPP.client                                            ](mppclient)
  - [MPP.client.canConnect                               ](mppclientcanconnect)
  - [MPP.client.channel                                  ](mppclientchannel)
  - [MPP.client.connectionAttempts                       ](mppclientconnectionattempts)
  - [MPP.client.connectionTime                           ](mppclientconnectiontime)
  - [MPP.client.desiredChannelId                         ](mppclientdesiredchannelid)
  - [MPP.client.desiredChannelSettings                   ](mppclientdesiredchannelsettings)
  - [MPP.client.noteBuffer                               ](mppclientnotebuffer)
  - [MPP.client.noteBufferTime                           ](mppclientnotebuffertime)
  - [MPP.client.noteFlushInterval                        ](mppclientnoteflushinterval)
  - [MPP.client.participantId                            ](mppclientparticipantid)
  - [MPP.client.pingInterval                             ](mppclientpinginterval)
  - [MPP.client.ppl                                      ](mppclientppl)
  - [MPP.client.serverTimeOffset                         ](mppclientservertimeoffset)
  - [MPP.client.uri                                      ](mppclienturi)
  - [MPP.client.user                                     ](mppclientuser)
  - [MPP.client.ws                                       ](mppclientws)
  - [MPP.client.bindEventListeners()                     ](mppclientbindeventlisteners)
  - [MPP.client.connect()                                ](mppclientconnect)
  - [MPP.client.countParticipants()                      ](mppclientcountparticipants)
  - [MPP.client.emit(evtn)                               ](mppclientemitevtn)
  - [MPP.client.findParticipantById(id)                  ](mppclientfindparticipantbyidid)
  - [MPP.client.getChannelSetting(key)                   ](mppclientgetchannelsettingkey)
  - [MPP.client.getOwnParticipant()                      ](mppclientgetownparticipant)
  - [MPP.client.isConnected()                            ](mppclientisconnected)
  - [MPP.client.isConnecting()                           ](mppclientisconnecting)
  - [MPP.client.isOwner()                                ](mppclientisowner)
  - [MPP.client.isSupported()                            ](mppclientissupported)
  - [MPP.client.off(evnt, fn)                            ](mppclientoffevnt-fn)
  - [MPP.client.offlineChannelSettings                   ](mppclientofflinechannelsettings)
  - [MPP.client.offlineParticipant                       ](mppclientofflineparticipant)
  - [MPP.client.on(evtn, fn)                             ](mppclientonevtn-fn)
  - [MPP.client.participantUpdate(update)                ](mppclientparticipantupdateupdate)
  - [MPP.client.preventsPlaying                          ](mppclientpreventsplaying)
  - [MPP.client.receiveServerTime(time, echo)            ](mppclientreceiveservertimetime-echo)
  - [MPP.client.send(raw)                                ](mppclientsendraw)
  - [MPP.client.sendArray(arr)                           ](mppclientsendarrayarr)
  - [MPP.client.setChannel(id, [set])                    ](mppclientsetchannelid-set)
  - [MPP.client.setParticipants(ppl)                     ](mppclientsetparticipantsppl)
  - [MPP.client.start()                                  ](mppclientstart)
  - [MPP.client.startNote(note, [vel])                   ](mppclientstartnotenote-vel)
  - [MPP.client.stop()                                   ](mppclientstop)
  - [MPP.client.stopNote(note)                           ](mppclientstopnotenote)
- [MPP.chat                                              ](mppchat)
  - [MPP.chat.blur()                                     ](mppchatblur)
  - [MPP.chat.clear()                                    ](mppchatclear)
  - [MPP.chat.hide()                                     ](mppchathide)
  - [MPP.chat.receive(msg)                               ](mppchatreceivemsg)
  - [MPP.chat.scrollToBottom()                           ](mppchatscrolltobottom)
  - [MPP.chat.send(message)                              ](mppchatsendmessage)
  - [MPP.chat.show()                                     ](mppchatshow)
  - [event: "a"                                          ](mppclient-event-a)
  - [event: "bye"                                        ](mppclient-event-bye)
  - [event: "c"                                          ](mppclient-event-c)
  - [event: "ch"                                         ](mppclient-event-ch)
  - [event: "connect"                                    ](mppclient-event-connect)
  - [event: "count"                                      ](mppclient-event-count)
  - [event: "disconnect"                                 ](mppclient-event-disconnect)
  - [event: "hi"                                         ](mppclient-event-hi)
  - [event: "ls"                                         ](mppclient-event-ls)
  - [event: "m"                                          ](mppclient-event-m)
  - [event: "n"                                          ](mppclient-event-n)
  - [event: "notification"                               ](mppclient-event-notification)
  - [event: "nq"                                         ](mppclient-event-nq)
  - [event: "p"                                          ](mppclient-event-p)
  - [event: "participant added"                          ](mppclient-event-participant-added)
  - [event: "participant removed"                        ](mppclient-event-participant-removed)
  - [event: "participant update"                         ](mppclient-event-participant-update)
  - [event: "status"                                     ](mppclient-event-status)
  - [event: "t"                                          ](mppclient-event-t)
- [MPP.noteQuota                                         ](mppnotequota)
  - [MPP.noteQuota.allowance                             ](mppnotequotaallowance)
  - [MPP.noteQuota.cb(points)                            ](mppnotequotacbpoints)
  - [MPP.noteQuota.histLen                               ](mppnotequotahistlen)
  - [MPP.noteQuota.history                               ](mppnotequotahistory)
  - [MPP.noteQuota.max                                   ](mppnotequotamax)
  - [MPP.noteQuota.points                                ](mppnotequotapoints)
  - [MPP.noteQuota.getParams()                           ](mppnotequotagetparams)
  - [MPP.noteQuota.resetPoints()                         ](mppnotequotaresetpoints)
  - [MPP.noteQuota.setParams(params)                     ](mppnotequotasetparamsparams)
  - [MPP.noteQuota.spend(needed)                         ](mppnotequotaspendneeded)
  - [MPP.noteQuota.tick()                                ](mppnotequotatick)
- [MPP.soundSelector                                     ](mppsoundselector)
  - [MPP.soundSelector.initialized                       ](mppsoundselectorinitialized)
  - [MPP.soundSelector.keys                              ](mppsoundselectorkeys)
  - [MPP.soundSelector.loading                           ](mppsoundselectorloading)
  - [MPP.soundSelector.packs                             ](mppsoundselectorpacks)
  - [MPP.soundSelector.piano                             ](mppsoundselectorpiano)
  - [MPP.soundSelector.soundSelection                    ](mppsoundselectorsoundselection)
  - [MPP.soundSelector.addPack(pack, load)               ](mppsoundselectoraddpackpack-load)
  - [MPP.soundSelector.addPacks(packs)                   ](mppsoundselectoraddpackspacks)
  - [MPP.soundSelector.init()                            ](mppsoundselectorinit)
  - [MPP.soundSelector.loadPack(pack, f)                 ](mppsoundselectorloadpackpack-f)
  - [MPP.soundSelector.removePack(name)                  ](mppsoundselectorremovepackname)



### MPP.press(id, vol)
- `id` <String> the id of the key, such as `a1`
- `vol` <Number> velocity of the key press; ranges from 0-1

Presses a key as the user, consuming note quota and sending it to other participants.


### MPP.release(id)
- `id` <String> the id of the key, such as `a1`

Releases a key pressed by MPP.press


### MPP.piano
- class: [Piano]


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
### MPP.client.canConnect
### MPP.client.channel
### MPP.client.connectionAttempts
### MPP.client.connectionTime
### MPP.client.desiredChannelId
### MPP.client.desiredChannelSettings
### MPP.client.noteBuffer
### MPP.client.noteBufferTime
### MPP.client.noteFlushInterval
### MPP.client.participantId
### MPP.client.pingInterval
### MPP.client.ppl
### MPP.client.serverTimeOffset
### MPP.client.uri
### MPP.client.user
### MPP.client.ws
### MPP.client.bindEventListeners()
### MPP.client.connect()
### MPP.client.countParticipants()
### MPP.client.emit(evtn)
### MPP.client.findParticipantById(id)
### MPP.client.getChannelSetting(key)
### MPP.client.getOwnParticipant()
### MPP.client.isConnected()
### MPP.client.isConnecting()
### MPP.client.isOwner()
### MPP.client.isSupported()
### MPP.client.off(evnt, fn)
### MPP.client.offlineChannelSettings
### MPP.client.offlineParticipant
### MPP.client.on(evtn, fn)
### MPP.client.participantUpdate(update)
### MPP.client.preventsPlaying
### MPP.client.receiveServerTime(time, echo)
### MPP.client.send(raw)
### MPP.client.sendArray(arr)
### MPP.client.setChannel(id, [set])
### MPP.client.setParticipants(ppl)
### MPP.client.start()
### MPP.client.startNote(note, [vel])
### MPP.client.stop()
### MPP.client.stopNote(note)
### MPP.chat
### MPP.chat.blur()
### MPP.chat.clear()
### MPP.chat.hide()
### MPP.chat.receive(msg)
### MPP.chat.scrollToBottom()
### MPP.chat.send(message)
### MPP.chat.show()
### MPP.client event: "a"
### MPP.client event: "bye"
### MPP.client event: "c"
### MPP.client event: "ch"
### MPP.client event: "connect"
### MPP.client event: "count"
### MPP.client event: "disconnect"
### MPP.client event: "hi"
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
