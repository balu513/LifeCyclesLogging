
Activity Callbacks:

Forward:
MainActivity. ——>.  Activity#A.  ——> Activity#B

Backword:
Activity#B —> Activity#A. ——> MainActivity

AppLaunch with MainActivity:

2020-06-06 22:06:19.976 25785-25785/com.balu.lifecycleslogging D/MainActivity: onCreate()
2020-06-06 22:06:19.979 25785-25785/com.balu.lifecycleslogging D/MainActivity: onStart()
2020-06-06 22:06:20.045 25785-25785/com.balu.lifecycleslogging D/MainActivity: onResume()
2020-06-06 22:06:20.514 25785-25785/com.balu.lifecycleslogging D/MainActivity: onCreateOptionsMenu()

A Activity Launches From MainActivity:

2020-06-06 22:07:04.618 25785-25785/com.balu.lifecycleslogging D/MainActivity: onPause()
2020-06-06 22:07:04.857 25785-25785/com.balu.lifecycleslogging D/A_Activity: onCreate()
2020-06-06 22:07:05.485 25785-25785/com.balu.lifecycleslogging D/A_Activity: onStart()
2020-06-06 22:07:05.487 25785-25785/com.balu.lifecycleslogging D/A_Activity: onResume()
2020-06-06 22:07:06.185 25785-25785/com.balu.lifecycleslogging D/A_Activity: onCreateOptionsMenu()
2020-06-06 22:07:06.810 25785-25785/com.balu.lifecycleslogging D/MainActivity: onStop()

B Activity Launches From A Activity:

2020-06-06 22:07:48.935 25785-25785/com.balu.lifecycleslogging D/A_Activity: onPause()
2020-06-06 22:07:49.053 25785-25785/com.balu.lifecycleslogging D/B_Activity: onCreate()
2020-06-06 22:07:49.682 25785-25785/com.balu.lifecycleslogging D/B_Activity: onStart()
2020-06-06 22:07:49.694 25785-25785/com.balu.lifecycleslogging D/B_Activity: onResume()
2020-06-06 22:07:50.069 25785-25785/com.balu.lifecycleslogging D/B_Activity: onCreateOptionsMenu()
2020-06-06 22:07:50.720 25785-25785/com.balu.lifecycleslogging D/A_Activity: onStop()


Back to A Activity From B Activity:

2020-06-06 22:08:24.233 25785-25785/com.balu.lifecycleslogging D/B_Activity: onPause()
2020-06-06 22:08:24.247 25785-25785/com.balu.lifecycleslogging D/A_Activity: onRestart()
2020-06-06 22:08:24.249 25785-25785/com.balu.lifecycleslogging D/A_Activity: onStart()
2020-06-06 22:08:24.250 25785-25785/com.balu.lifecycleslogging D/A_Activity: onResume()
2020-06-06 22:08:25.056 25785-25785/com.balu.lifecycleslogging D/B_Activity: onStop()
2020-06-06 22:08:25.059 25785-25785/com.balu.lifecycleslogging D/B_Activity: onDestroy()

Back to MainActivity from A Activity:

2020-06-06 22:09:12.329 25785-25785/com.balu.lifecycleslogging D/A_Activity: onPause()
2020-06-06 22:09:12.338 25785-25785/com.balu.lifecycleslogging D/MainActivity: onRestart()
2020-06-06 22:09:12.340 25785-25785/com.balu.lifecycleslogging D/MainActivity: onStart()
2020-06-06 22:09:12.342 25785-25785/com.balu.lifecycleslogging D/MainActivity: onResume()
2020-06-06 22:09:13.138 25785-25785/com.balu.lifecycleslogging D/A_Activity: onStop()
2020-06-06 22:09:13.138 25785-25785/com.balu.lifecycleslogging D/A_Activity: onDestroy()





Fragment Callbacks (by replace):
By  —  getSupportFragmentManager().beginTransaction().replace(R.id.framelayout, fragment);

Forward:
Activity#B   —->  Act#C - Fragment#A.   —->    Fragment #B

By back
Fragment#B.   -—>.   Fragment#A.   -—>.  Activity#C(empty screen) —-> Activity#B



Activity #B -> Activity #C ( onCreate() loaded Fragment#A ) :-

2020-06-06 22:10:17.766 25785-25785/com.balu.lifecycleslogging D/C_Activity: onCreate()
2020-06-06 22:10:17.772 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onAttach
2020-06-06 22:10:17.772 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onCreate
2020-06-06 22:10:17.773 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onCreateView
2020-06-06 22:10:17.889 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onActivityCreated
2020-06-06 22:10:17.891 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onStart
2020-06-06 22:10:17.899 25785-25785/com.balu.lifecycleslogging D/C_Activity: onStart()
2020-06-06 22:10:17.949 25785-25785/com.balu.lifecycleslogging D/C_Activity: onResume()
2020-06-06 22:10:17.952 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onResume
2020-06-06 22:10:18.351 25785-25785/com.balu.lifecycleslogging D/C_Activity: onCreateOptionsMenu()
2020-06-06 22:10:19.030 25785-25785/com.balu.lifecycleslogging D/B_Activity: onStop()


Fragment#B from Fragment#A. (By fragment transaction replace call) :-

2020-06-06 22:13:00.223 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onAttach
2020-06-06 22:13:00.224 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onCreate
2020-06-06 22:13:00.225 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onPause
2020-06-06 22:13:00.225 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onStop
2020-06-06 22:13:00.225 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onDestroyView
2020-06-06 22:13:00.233 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onCreateView
2020-06-06 22:13:00.271 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onActivityCreated
2020-06-06 22:13:00.271 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onStart
2020-06-06 22:13:00.273 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onResume

By Backbutton (going back to Fragment A. From Fragment B) :-

2020-06-06 22:15:01.367 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onPause
2020-06-06 22:15:01.368 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onStop
2020-06-06 22:15:01.370 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onDestroyView
2020-06-06 22:15:01.374 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onDestroy
2020-06-06 22:15:01.374 25785-25785/com.balu.lifecycleslogging D/B_Fragment: onDetach
2020-06-06 22:15:01.375 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onCreateView
2020-06-06 22:15:01.419 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onActivityCreated
2020-06-06 22:15:01.423 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onStart
2020-06-06 22:15:01.425 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onResume

By BackButton (going back from Fragment A) :-

20-06-06 22:16:00.702 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onPause
2020-06-06 22:16:00.702 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onStop
2020-06-06 22:16:00.702 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onDestroyView
2020-06-06 22:16:00.706 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onDestroy
2020-06-06 22:16:00.706 25785-25785/com.balu.lifecycleslogging D/A_Fragment: onDetach
(Displaying EMPTY screen Now). Means detached A fragment inside C Activity.


Again BackButton click (empty Actvity#C to Activity#B):-

2020-06-06 22:17:23.443 25785-25785/com.balu.lifecycleslogging D/C_Activity: onPause()
2020-06-06 22:17:23.465 25785-25785/com.balu.lifecycleslogging D/B_Activity: onRestart()
2020-06-06 22:17:23.472 25785-25785/com.balu.lifecycleslogging D/B_Activity: onStart()
2020-06-06 22:17:23.477 25785-25785/com.balu.lifecycleslogging D/B_Activity: onResume()
2020-06-06 22:17:24.356 25785-25785/com.balu.lifecycleslogging D/C_Activity: onStop()
2020-06-06 22:17:24.364 25785-25785/com.balu.lifecycleslogging D/C_Activity: onDestroy()



Fragment Callbacks:  (by Add)
By  —  getSupportFragmentManager().beginTransaction().add(R.id.framelayout, fragment);

Forward:
Activity#B   —->  Act#C - Fragment#A.   —->    Fragment #B

By back
Fragment#B.   -—>.   Fragment#A.   -—>.  Activity#C(empty screen) —-> Activity#B


Activity #B -> Activity #C ( onCreate() loaded Fragment#A ) :-

2020-06-06 22:31:26.734 28252-28252/com.balu.lifecycleslogging D/B_Activity: onPause()
2020-06-06 22:31:27.100 28252-28252/com.balu.lifecycleslogging D/C_Activity: onCreate()
2020-06-06 22:31:27.143 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onAttach
2020-06-06 22:31:27.144 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onCreate
2020-06-06 22:31:27.181 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onCreateView
2020-06-06 22:31:27.390 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onActivityCreated
2020-06-06 22:31:27.412 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onStart
2020-06-06 22:31:27.468 28252-28252/com.balu.lifecycleslogging D/C_Activity: onStart()
2020-06-06 22:31:27.472 28252-28252/com.balu.lifecycleslogging D/C_Activity: onResume()
2020-06-06 22:31:27.490 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onResume
2020-06-06 22:31:27.961 28252-28252/com.balu.lifecycleslogging D/C_Activity: onCreateOptionsMenu()
2020-06-06 22:31:28.642 28252-28252/com.balu.lifecycleslogging D/B_Activity: onStop()

Fragment#B from Fragment#A. (By fragment transaction add call) :-

2020-06-06 22:32:29.806 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onAttach
2020-06-06 22:32:29.806 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onCreate
2020-06-06 22:32:29.808 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onCreateView
2020-06-06 22:32:29.879 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onActivityCreated
2020-06-06 22:32:29.880 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onStart
2020-06-06 22:32:29.882 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onResume


By Backbutton (going back to Fragment A. From Fragment B) :-

2020-06-06 22:33:08.648 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onPause
2020-06-06 22:33:08.648 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onStop
2020-06-06 22:33:08.648 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onDestroyView
2020-06-06 22:33:08.653 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onDestroy
2020-06-06 22:33:08.653 28252-28252/com.balu.lifecycleslogging D/B_Fragment: onDetach

By BackButton (going back from Fragment A) :-

2020-06-06 22:33:54.628 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onPause
2020-06-06 22:33:54.631 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onStop
2020-06-06 22:33:54.633 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onDestroyView
2020-06-06 22:33:54.635 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onDestroy
2020-06-06 22:33:54.635 28252-28252/com.balu.lifecycleslogging D/A_Fragment: onDetach
(Displaying EMPTY screen Now). Means detached A fragment inside C Activity.

Again BackButton click :- (empty Actvity#C to Activity#B)

2020-06-06 22:36:01.840 28252-28252/com.balu.lifecycleslogging D/C_Activity: onPause()
2020-06-06 22:36:01.873 28252-28252/com.balu.lifecycleslogging D/B_Activity: onRestart()
2020-06-06 22:36:01.892 28252-28252/com.balu.lifecycleslogging D/B_Activity: onStart()
2020-06-06 22:36:01.912 28252-28252/com.balu.lifecycleslogging D/B_Activity: onResume()
2020-06-06 22:36:03.100 28252-28252/com.balu.lifecycleslogging D/C_Activity: onStop()
2020-06-06 22:36:03.103 28252-28252/com.balu.lifecycleslogging D/C_Activity: onDestroy()


NOTE :    if you press HomeButton at any time launches HomeScreenActivity(Launcherscree) on top of current screen. (Like, calling other activity on top of current Activity or Fragment)












