Classical Music Quiz:

The second commit adds the Exoplayer Functionality by implementing a SimpleExoPlayer - including adding TrackSelector, LoadControl, ExtractorFactory (to add MediaSource), and DataSource; also adding default artwork, and handling life-cycle callbacks.

The third commit overwrites the exo_playback_control_view.xml which has been added to the layout directory in order to delete the "next song" and "last song" buttons.  The version of exoplayer has been maintained at 2.6.1.

This fourth commit adds an Exoplayer event listener together with all of its required overrides.  At this stage the onPlayerStateChanged() method will be used to log play and pause events, but this will serve as the way the app will communicate with a Media Session (to be added in subsequent steps).