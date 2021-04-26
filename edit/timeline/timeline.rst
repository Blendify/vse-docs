***************
Timeline basics
***************

.. toctree::
    :maxdepth: 3
  
    timecode/timecode.rst
    zoom/zoom.rst
    navigate/navigate.rst
    scrub/scrub.rst
  
The concept *Timeline* can refer to different things. In Blender, it denotes in the first place the `Timeline Editor <https://docs.blender.org/manual/en/dev/editors/timeline.html>`_ , identified by a clock icon, and used for manipulating keyframes and scrubbing the playhead. This Timeline Editor was originally intended for editing the animations in 3D modeling.

.. figure:: timeline-editor.svg
   :alt: Timeline editor

   Figure 1: The Timeline Editor in Blender

You can find this Timeline Editor also in the :doc:`Video Sequence Editor workspace </setup/customize/workspace/video-editing-workspace>`, all the way at the bottom of the screen. Only the header is visible; so you have to drag the horizontal top border to reveal the time codes and keyframes.

The use of this Timeline Editor within the Video Editor workspace is however rather limited and its functions can easily be overtaken by the Sequencer, which is right on top of it. An exception is perhaps the Auto keyframing button and the xxx. The record button (⏺) enables Auto Keyframe. It will add and/or replace existing keyframes for the selected strip when you change some properties; for example the Opacity to create a Fade effect. transform it in the 3D Viewport. 
The Sequencer however has also a kind of timeline on its own: the area where the strip bars are painted. Practically all the regular operations like zoom, navigate, ... can be done here. Only the Frame and Transport controls are missing.

.. figure:: timeline-sequencer.svg
   :alt: Sequencer timeline

   Figure 2: The timeline of the SequencerTimeline Editor in Blender


These can however easily be added to the workspace (see the addon by TintwoTin; `Playback_control_in_VSE_header.zip <https://github.com/tin2tin/Sequence_Editing>`_ ). 

In Blender you can choose to show the timeline in seconds or in frames (menu View > Show seconds). As a video editor, you probably are most interested in the :doc:`SMPTE-timecode <timecode/timecode>`. It seems more natural to refer to a video fragment with a time indication, e.g. 00:01:15:10 or 1' 15'' and 10 frames than with a frame number, e.g. frame 55.

.. note::
   Don't make the mistake to think that timecode is equal to time. For modern video file, all the time information, you'll get is the timestamp at the start of the recording and the duration in frames of the video. So, the time codes are calculated by the software. And there it could go wrong. If your project has a project framerate of 30 fps and your imported footage is hot with a framerate of 24 fps, the timecode that you see will always refer to the project. So, the code 00:00:02:6 will refer to frame 36 which is at 2.2 seconds from the start. However, this 36th frame was at 2.5 seconds from the start in the raw footage. If there was an explosion at that moment in time, it will occur later in your project and will be associated with the wrong frame image. 

The time code 01:21+11 indicates "1 minute and 21 seconds and 11 frames". Because each project has a frame-per-seconds `fps` parameter, you can always derive one code from the other. In a 30 fps project:

* frame 155 is at time 115/30 = 3.8333 seconds or in Blender notation: 00:03+25.
* time 2.5s falls within frame  2.5 * 30 = 75.