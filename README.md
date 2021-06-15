# unity-dots-ecs-017-android-release-crash
Created for or bugreport;

Reproducible with: 2020.3.11f1

Steps to reproduce:
1.Create empty project in Unity with simple scene 
2.Add packages:  
```
    "com.unity.burst": "1.5.4",
    "com.unity.entities": "0.17.0-preview.42",
```
3. Switch build to Android. Set release.  Set IL2CPP.
4. Build and Run on device.
5. Get crash on start

If downgrade entities to 0.16 or make dev.build - no crash  

stacktrace:

```
2021/06/15 13:47:11.476 32609 32636 Error CRASH *** *** *** *** *** *** *** *** *** *** *** *** *** *** *** ***
2021/06/15 13:47:11.476 32609 32636 Error CRASH Version '2020.3.2f1 (8fd9074bf66c)', Build type 'Release', Scripting Backend 'il2cpp', CPU 'arm64-v8a'
2021/06/15 13:47:11.476 32609 32636 Error CRASH Build fingerprint: 'Sony/XQ-AT51_RU/[...]'
2021/06/15 13:47:11.476 32609 32636 Error CRASH Revision: '0'
2021/06/15 13:47:11.476 32609 32636 Error CRASH ABI: 'arm64'
2021/06/15 13:47:11.476 32609 32636 Error CRASH Timestamp: 2021-06-15 13:47:11+0300
2021/06/15 13:47:11.476 32609 32636 Error CRASH pid: 32609, tid: 32636, name: UnityMain  >>> com.DefaultCompany.unitydotsecs017androidreleasecrash <<<
2021/06/15 13:47:11.476 32609 32636 Error CRASH uid: 10487
2021/06/15 13:47:11.476 32609 32636 Error CRASH signal 11 (SIGSEGV), code 1 (SEGV_MAPERR), fault addr 0xc
2021/06/15 13:47:11.476 32609 32636 Error CRASH Cause: null pointer dereference
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x0  0000006be8272700  x1  0000007022ddf564  x2  0000006cc8888198  x3  00000000000000f0
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x4  0000000000000010  x5  0000006be82727f6  x6  006f006d00650052  x7  0041006400650076
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x8  0000000000000001  x9  0000000000000000  x10 000000000000000e  x11 0000000000000120
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x12 0000000000000000  x13 0020007200650074  x14 0001000000000000  x15 00000000000003d1
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x16 0000006cc6776fe0  x17 0000007022d43abc  x18 00000000e843421b  x19 0000000000000000
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x20 0000006be81f99c0  x21 0000006cc681e000  x22 0000006cc67fb180  x23 0000006cc67ea2e8
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x24 0000000000000000  x25 0000006cc888a000  x26 000000000000056a  x27 0000000000000001
2021/06/15 13:47:11.476 32609 32636 Error CRASH     x28 0000000000000000  x29 0000006cc8888280
2021/06/15 13:47:11.476 32609 32636 Error CRASH     sp  0000006cc8888250  lr  0000006cc5dc8228  pc  0000006cc5dc8230
2021/06/15 13:47:11.476 32609 32636 Error CRASH backtrace:
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #00 pc 00000000008bc230 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #01 pc 00000000008b0180 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #02 pc 0000000000414a04 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #03 pc 0000000000361568 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #04 pc 00000000002186cc (AtomicNode* DSPGraph::FetchCommandNode<AddAttenuationKeyCommand, DSPConnectionHandle&, unsigned long&, float, bool>(DSPConnectionHandle&, unsigned long&, float&&, bool&&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #05 pc 0000000000226924 (void JSONRead::Transfer<std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> > >(std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> >&, char const*, TransferMetaFlags, bool) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #06 pc 0000000000184d20 (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #07 pc 0000000000184c7c (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #08 pc 00000000001842a4 (PPtr<AnimationClip>::operator AnimationClip*() const at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #09 pc 0000000000197f10 (dynamic_array<AnimatedProperty*, 0ul>::clear_dealloc() at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #10 pc 0000000000197bd8 (void std::__ndk1::vector<AvatarFrame, std::__ndk1::allocator<AvatarFrame> >::__push_back_slow_path<AvatarFrame const&>(AvatarFrame const&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #11 pc 0000000000197e94 (AnimatedPropertyEvaluator::BindCurveToScriptingObjectPtr(AnimationClip::FloatCurve const&, unsigned int, ScriptingObjectPtr, bool) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #12 pc 00000000001978c8 (dynamic_array<unsigned char, 16ul>::~dynamic_array() at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #13 pc 0000000000197988 (void BlobWrite::Transfer<mecanim::animation::AvatarMemory>(mecanim::animation::AvatarMemory&, char const*, TransferMetaFlags) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #14 pc 000000000019765c (void StreamedBinaryRead::TransferSTLStyleArray<core::basic_string<char, core::StringStorageDefault<char> > >(core::basic_string<char, core::StringStorageDefault<char> >&, TransferMetaFlags) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #15 pc 0000000000198594 (e843419@0091_00001b13_1c at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #16 pc 0000000000198adc (e843419@0091_00001b13_1c at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #17 pc 00000000002908c4 (Shader* VFXTaskDesc::GetProcessor<Shader>() const at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #18 pc 00000000002a43f0 (void AssetBundle::Transfer<GenerateTypeTreeTransfer>(GenerateTypeTreeTransfer&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.476 32609 32636 Error CRASH       #19 pc 00000000000040ec  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/oat/arm64/base.odex
2021/06/15 13:47:11.531 32609 32636 Error CRASH Tombstone written to: /storage/emulated/0/Android/data/com.DefaultCompany.unitydotsecs017androidreleasecrash/files/tombstone_01
0001/01/01 00:00:00.000 -1 -1 Info  --------- beginning of crash
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime FATAL EXCEPTION: UnityMain
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Process: com.DefaultCompany.unitydotsecs017androidreleasecrash, PID: 32609
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime java.lang.Error: *** *** *** *** *** *** *** *** *** *** *** *** *** *** *** ***
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Version '2020.3.2f1 (8fd9074bf66c)', Build type 'Release', Scripting Backend 'il2cpp', CPU 'arm64-v8a'
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Build fingerprint: 'Sony/XQ-AT51_RU/XQ-AT51:11/58.1.A.5.222A/058001A0050222A2757098914:user/release-keys'
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Revision: '0'
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime ABI: 'arm64'
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Timestamp: 2021-06-15 13:47:11+0300
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime pid: 32609, tid: 32636, name: UnityMain  >>> com.DefaultCompany.unitydotsecs017androidreleasecrash <<<
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime uid: 10487
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime signal 11 (SIGSEGV), code 1 (SEGV_MAPERR), fault addr 0xc
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime Cause: null pointer dereference
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x0  0000006be8272700  x1  0000007022ddf564  x2  0000006cc8888198  x3  00000000000000f0
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x4  0000000000000010  x5  0000006be82727f6  x6  006f006d00650052  x7  0041006400650076
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x8  0000000000000001  x9  0000000000000000  x10 000000000000000e  x11 0000000000000120
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x12 0000000000000000  x13 0020007200650074  x14 0001000000000000  x15 00000000000003d1
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x16 0000006cc6776fe0  x17 0000007022d43abc  x18 00000000e843421b  x19 0000000000000000
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x20 0000006be81f99c0  x21 0000006cc681e000  x22 0000006cc67fb180  x23 0000006cc67ea2e8
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x24 0000000000000000  x25 0000006cc888a000  x26 000000000000056a  x27 0000000000000001
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     x28 0000000000000000  x29 0000006cc8888280
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime     sp  0000006cc8888250  lr  0000006cc5dc8228  pc  0000006cc5dc8230
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime backtrace:
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #00 pc 00000000008bc230 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #01 pc 00000000008b0180 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #02 pc 0000000000414a04 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #03 pc 0000000000361568 (libil2cpp.so not found)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libil2cpp.so (BuildId: 8705256d5a2142eb3c4a353c2392369f0f108933)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #04 pc 00000000002186cc (AtomicNode* DSPGraph::FetchCommandNode<AddAttenuationKeyCommand, DSPConnectionHandle&, unsigned long&, float, bool>(DSPConnectionHandle&, unsigned long&, float&&, bool&&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #05 pc 0000000000226924 (void JSONRead::Transfer<std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> > >(std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> >&, char const*, TransferMetaFlags, bool) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #06 pc 0000000000184d20 (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #07 pc 0000000000184c7c (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #08 pc 00000000001842a4 (PPtr<AnimationClip>::operator AnimationClip*() const at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #09 pc 0000000000197f10 (dynamic_array<AnimatedProperty*, 0ul>::clear_dealloc() at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #10 pc 0000000000197bd8 (void std::__ndk1::vector<AvatarFrame, std::__ndk1::allocator<AvatarFrame> >::__push_back_slow_path<AvatarFrame const&>(AvatarFrame const&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #11 pc 0000000000197e94 (AnimatedPropertyEvaluator::BindCurveToScriptingObjectPtr(AnimationClip::FloatCurve const&, unsigned int, ScriptingObjectPtr, bool) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #12 pc 00000000001978c8 (dynamic_array<unsigned char, 16ul>::~dynamic_array() at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #13 pc 0000000000197988 (void BlobWrite::Transfer<mecanim::animation::AvatarMemory>(mecanim::animation::AvatarMemory&, char const*, TransferMetaFlags) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #14 pc 000000000019765c (void StreamedBinaryRead::TransferSTLStyleArray<core::basic_string<char, core::StringStorageDefault<char> > >(core::basic_string<char, core::StringStorageDefault<char> >&, TransferMetaFlags) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #15 pc 0000000000198594 (e843419@0091_00001b13_1c at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #16 pc 0000000000198adc (e843419@0091_00001b13_1c at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #17 pc 00000000002908c4 (Shader* VFXTaskDesc::GetProcessor<Shader>() const at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #18 pc 00000000002a43f0 (void AssetBundle::Transfer<GenerateTypeTreeTransfer>(GenerateTypeTreeTransfer&) at ??:?)  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/lib/arm64/libunity.so (BuildId: ccd4a51df53692fb7e10252ab3aa22e8f221cc3b)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime       #19 pc 00000000000040ec  /data/app/~~E-22Migi_RlB_YfnW2lXug==/com.DefaultCompany.unitydotsecs017androidreleasecrash-5ROMOL-OX6_vvFSbS3kW0Q==/oat/arm64/base.odex
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libil2cpp.0x8bc230 (libil2cpp.so not found)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libil2cpp.0x8b0180 (libil2cpp.so not found)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libil2cpp.0x414a04 (libil2cpp.so not found)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libil2cpp.0x361568 (libil2cpp.so not found)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x2186cc (AtomicNode* DSPGraph::FetchCommandNode<AddAttenuationKeyCommand, DSPConnectionHandle&, unsigned long&, float, bool>(DSPConnectionHandle&, unsigned long&, float&&, bool&&) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x226924 (void JSONRead::Transfer<std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> > >(std::__ndk1::vector<core::string_with_label<1, char>, stl_allocator<core::string_with_label<1, char>, (MemLabelIdentifier)1, 16> >&, char const*, TransferMetaFlags, bool) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x184d20 (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x184c7c (Animation::QueueCrossFade(AnimationState&, float, int, Animation::PlayMode) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x1842a4 (PPtr<AnimationClip>::operator AnimationClip*() const at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x197f10 (dynamic_array<AnimatedProperty*, 0ul>::clear_dealloc() at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x197bd8 (void std::__ndk1::vector<AvatarFrame, std::__ndk1::allocator<AvatarFrame> >::__push_back_slow_path<AvatarFrame const&>(AvatarFrame const&) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x197e94 (AnimatedPropertyEvaluator::BindCurveToScriptingObjectPtr(AnimationClip::FloatCurve const&, unsigned int, ScriptingObjectPtr, bool) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x1978c8 (dynamic_array<unsigned char, 16ul>::~dynamic_array() at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x197988 (void BlobWrite::Transfer<mecanim::animation::AvatarMemory>(mecanim::animation::AvatarMemory&, char const*, TransferMetaFlags) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x19765c (void StreamedBinaryRead::TransferSTLStyleArray<core::basic_string<char, core::StringStorageDefault<char> > >(core::basic_string<char, core::StringStorageDefault<char> >&, TransferMetaFlags) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x198594 (e843419@0091_00001b13_1c at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x198adc (e843419@0091_00001b13_1c at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x2908c4 (Shader* VFXTaskDesc::GetProcessor<Shader>() const at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at libunity.0x2a43f0 (void AssetBundle::Transfer<GenerateTypeTreeTransfer>(GenerateTypeTreeTransfer&) at ??:?)(Native Method)
2021/06/15 13:47:11.531 32609 32636 Error AndroidRuntime 	at base.0x40ec(Native Method)
```

    