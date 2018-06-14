Classical Music Quiz:

The second commit adds the Exoplayer Functionality by implementing a SimpleExoPlayer - including adding TrackSelector, LoadControl, ExtractorFactory (to add MediaSource), and DataSource; also adding default artwork, and handling life-cycle callbacks.

The third commit overwrites the exo_playback_control_view.xml which has been added to the layout directory in order to delete the "next song" and "last song" buttons. The version of exoplayer has been maintained at 2.6.1.

The fourth commit adds an Exoplayer event listener together with all of its required overrides. At this stage the onPlayerStateChanged() method will be used to log play and pause events, but this will serve as the way the app will communicate with a Media Session (to be added in subsequent steps).

The fifth commit adds a Media Session and establishes a two-way communication between the Media Session and both a Media Controller and the ExoPlayer.  The onPlayerStateChanged() method enables the Media Session to be updated with the current state of the ExoPlayer.  The callbacks in the inner class I named "mediaCallbacksPlus" which extends MediaSessionCompat.Callback are called by the Media Controller and are populated with code that change the state of the exoplayer.  This completes the two-way communication.

This final sixth commit combines the 4th and 5th exercises in this lesson, "Add Media Notification" and "Add Media Button Receiver", which makes sense because the Media Notification will not operate properly without a Media Button Receiver since the notification contains added Actions with PendingIntents that communicate with the Exoplayer to start, pause, or rewind the current playing classical music selection (the selection will play in the background if the app is closed).  In this exercise the Media Notification approximates the action of an external Media Controller and verifies that all the callbacks are correct.