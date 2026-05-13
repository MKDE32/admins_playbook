# PROPERTIES
- doh
  - settings → privacy & security → DNS over HTTPS > max protection
- https only
  - settings → privacy & security → HTTPS-Only Mode
- sicherheit max
  - settings > privacy & security > strict
- autoplay
  - settings > privacy & security > permissions > block
- tracking protection
  - settings → privacy & security > strict






# ABOUT:CONFIG
- preload / speculative
  - network.dns.disablePrefetch = true
  - network.prefetch-next = false
  - network.http.speculative-parallel-limit = 0
- dns leak
  - network.trr.mode > 3
- fingerprinting resistance
  - privacy.resistFingerprinting = true
- webrtc
  - media.peerconnection.enabled = false
- telemetry
  - toolkit.telemetry.enabled = false
  - datareporting.healthreport.uploadEnabled = false
  - app.shield.optoutstudies.enabled = false




# ADD ONS
- ublock
- malwarebytes
- noscript
- firefox multi-account container

















