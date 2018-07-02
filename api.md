# Multiplayer Piano API Documentation

## Table of Contents
- MPP.press(id, vol)
- MPP.release(id)
- MPP.piano
  - MPP.piano.audio
    - MPP.piano.audio.context
    - MPP.piano.audio.limiterNode
    - MPP.piano.audio.paused
    - MPP.piano.audio.pianoGain
    - MPP.piano.audio.playings
    - MPP.piano.audio.sounds
    - MPP.piano.audio.synthGain
    - MPP.piano.audio.threshold
    - MPP.piano.audio.volume
    - MPP.piano.audio.worker
    - MPP.piano.audio.actualPlay(id, vol, time, part_id)
    - MPP.piano.audio.actualStop(id, time, part_id)
    - MPP.piano.audio.init(cb)
    - MPP.piano.audio.load(id, url, cb)
    - MPP.piano.audio.play(id, vol, delay_ms, part_id)
    - MPP.piano.audio.resume()
    - MPP.piano.audio.setVolume(vol)
    - MPP.piano.audio.stop(id, delay_ms, part_id)
  - MPP.piano.play(id, vol, delay_ms, part_id)
  - MPP.piano.stop(note, participant, delay_ms)
  - MPP.piano.keys
  - MPP.piano.renderer
    - MPP.piano.renderer.blackBlipHeight
    - MPP.piano.renderer.blackBlipWidth
    - MPP.piano.renderer.blackBlipX
    - MPP.piano.renderer.blackBlipY
    - MPP.piano.renderer.blackKeyHeight
    - MPP.piano.renderer.blackKeyOffset
    - MPP.piano.renderer.blackKeyRender
    - MPP.piano.renderer.blackKeyWidth
    - MPP.piano.renderer.canvas
    - MPP.piano.renderer.ctx
    - MPP.piano.renderer.height
    - MPP.piano.renderer.keyMovement
    - MPP.piano.renderer.piano
    - MPP.piano.renderer.shadowRender
    - MPP.piano.renderer.whiteBlipHeight
    - MPP.piano.renderer.whiteBlipWidth
    - MPP.piano.renderer.whiteBlipX
    - MPP.piano.renderer.whiteBlipY
    - MPP.piano.renderer.whiteKeyHeight
    - MPP.piano.renderer.whiteKeyRender
    - MPP.piano.renderer.whiteKeyWidth
    - MPP.piano.renderer.width
    - MPP.piano.renderer.getHit(x, y)
    - MPP.piano.renderer.init(piano)
    - MPP.piano.renderer.redraw()
    - MPP.piano.renderer.resize(width, height)
    - MPP.piano.renderer.visualize(key, color)
  - MPP.piano.rootElement
- MPP.client
  - MPP.client.canConnect
  - MPP.client.channel
  - MPP.client.connectionAttempts
  - MPP.client.connectionTime
  - MPP.client.desiredChannelId
  - MPP.client.desiredChannelSettings
  - MPP.client.noteBuffer
  - MPP.client.noteBufferTime
  - MPP.client.noteFlushInterval
  - MPP.client.participantId
  - MPP.client.pingInterval
  - MPP.client.ppl
  - MPP.client.serverTimeOffset
  - MPP.client.uri
  - MPP.client.user
  - MPP.client.ws
  - MPP.client.bindEventListeners()
  - MPP.client.connect()
  - MPP.client.countParticipants()
  - MPP.client.emit(evtn)
  - MPP.client.findParticipantById(id)
  - MPP.client.getChannelSetting(key)
  - MPP.client.getOwnParticipant()
  - MPP.client.isConnected()
  - MPP.client.isConnecting()
  - MPP.client.isOwner()
  - MPP.client.isSupported()
  - MPP.client.off(evnt, fn)
  - MPP.client.offlineChannelSettings
  - MPP.client.offlineParticipant
  - MPP.client.on(evtn, fn)
  - MPP.client.participantUpdate(update)
  - MPP.client.preventsPlaying
  - MPP.client.receiveServerTime(time, echo)
  - MPP.client.send(raw)
  - MPP.client.sendArray(arr)
  - MPP.client.setChannel(id, [set])
  - MPP.client.setParticipants(ppl)
  - MPP.client.start()
  - MPP.client.startNote(note, [vel])
  - MPP.client.stop()
  - MPP.client.stopNote(note)
- MPP.chat
  - MPP.chat.blur()
  - MPP.chat.clear()
  - MPP.chat.hide()
  - MPP.chat.receive(msg)
  - MPP.chat.scrollToBottom()
  - MPP.chat.send(message)
  - MPP.chat.show()
  - event: "a"
  - event: "bye"
  - event: "c"
  - event: "ch"
  - event: "connect"
  - event: "count"
  - event: "disconnect"
  - event: "hi"
  - event: "ls"
  - event: "m"
  - event: "n"
  - event: "notification"
  - event: "nq"
  - event: "p"
  - event: "participant added"
  - event: "participant removed"
  - event: "participant update"
  - event: "status"
  - event: "t"
- MPP.noteQuota
  - MPP.noteQuota.allowance
  - MPP.noteQuota.cb(points)
  - MPP.noteQuota.histLen
  - MPP.noteQuota.history
  - MPP.noteQuota.max
  - MPP.noteQuota.points
  - MPP.noteQuota.getParams()
  - MPP.noteQuota.resetPoints()
  - MPP.noteQuota.setParams(params)
  - MPP.noteQuota.spend(needed)
  - MPP.noteQuota.tick()
- MPP.soundSelector
  - MPP.soundSelector.initialized
  - MPP.soundSelector.keys
  - MPP.soundSelector.loading
  - MPP.soundSelector.packs
  - MPP.soundSelector.piano
  - MPP.soundSelector.soundSelection
  - MPP.soundSelector.addPack(pack, load)
  - MPP.soundSelector.addPacks(packs)
  - MPP.soundSelector.init()
  - MPP.soundSelector.loadPack(pack, f)
  - MPP.soundSelector.removePack(name)



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
