# Attenuation of the signal

When a fully saturated or clipped input is applied to an SRC module, the aliases after the sample rate conversion, although sufficiently suppressed, can still result in a clipped output. To prevent clipped output, the output of the SSRC module is by default attenuated with 3 dB. Although not advised, this gain value can be changed using the SSRC\_SetGains function.

**Parent topic:**[Additional user information](../topics/additional_user_information.md)

