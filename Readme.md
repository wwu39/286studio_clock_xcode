Xcode Files Backup

如果Unity更新过版本可能不能直接覆盖UnityAppController.mm

保险做法：

打开生成的UnityAppController.mm

加上#include <AVFoundation/AVFoundation.h>

找到startUnity函数

在函数末尾加上以下语句：

[[AVAudioSession sharedInstance] setCategory:AVAudioSessionCategoryPlayback error:nil];

[[AVAudioSession sharedInstance] setActive:YES error: nil];

[[UIApplication sharedApplication] beginReceivingRemoteControlEvents];
