.. _course_structure:

####################
Course Content Data
####################

Each week, the database files include an 
``{org}-{course}-{date}-course_structure-{site}-analytics.json`` JSON file for
each course. Researchers can use this file to investigate course state at a
particular point in time.

This chapter describes the contents of the course structure file.

* :ref:`Course Structure Categories`
* :ref:`Course Data`
* :ref:`Course Building Block Data`
* :ref:`Course Component Data`

.. _Course Structure Categories:

******************************
Course Structure Categories
******************************

In the ``course_structure`` JSON file, a ``category`` field identifies each of
the structural elements of the course. This field contains one of the
following strings.

.. list-table::
   :widths: 25 60
   :header-rows: 1

   * - Category
     - Description
   * - chapter
     - The sections defined in the course outline. For more information, see
       :ref:`Course Building Block Data`.
   * - course
     - The dates, settings, and other metadata defined for the course as a
       whole. For more information, see :ref:`Course Data`.
   * - discussion
     - The content-specific discussion components defined for the course. For
       more information, see :ref:`Course Component Data`.
   * - html
     - The HTML components defined for the course. For more information, see
       :ref:`Course Component Data`.
   * - problem
     - The problem components defined for the course. For
       more information, see :ref:`Course Component Data`.
   * - sequential
     - The subsections defined in the course outline. For more information,
       see :ref:`Course Building Block Data`.
   * - vertical
     - The units defined in the course outline. For more information, see
       :ref:`Course Building Block Data`.
   * - video
     - The video components defined for the course. For more information, see
       :ref:`Course Component Data`.

The ``course_structure`` file contains additional category values for courses
that include other types of exercises or tools. For example, a category of
``poll_question`` identifies a Poll Tool component.

.. I am making this example up ^^


.. _Course Data:

***************
Course Data
***************


===================
Course Data Sample
===================

.. code-block:: json

   "i4x://edX/DemoX/course/1T2014": {
      "category": "course", 
      "children": [
        "i4x://edX/DemoX/chapter/1ff96c6155eb40c39140c656cdc2708b", 
        "i4x://edX/DemoX/chapter/00d4374f346b4744aa6f4708cdf46d53", 
        "i4x://edX/DemoX/chapter/abc5cf5203ee494faf73fa3f55b4485b", 
        "i4x://edX/DemoX/chapter/a783b6e59fe24917985a8aa29eeec150", 
        "i4x://edX/DemoX/chapter/0cdd0de7b1f740468381c265796f6f63"
      ], 
      "metadata": {
        "advertised_start": "9/9/2014", 
        "course_image": "Smiley Face Buttons_Horiz Crop_2.jpg", 
        "days_early_for_beta": 110.0, 
        "discussion_blackouts": [
          [
            "2014-12-02", 
            "2099-09-09"
          ]
        ], 
        "discussion_topics": {
          "Course Happiness Survey": {
            "id": "i4x-edX-GGSC101-course-2014_T1_survey"
          }, 
          "General": {
            "id": "i4x-edX-GGSC101-course-2014_T1"
          }
        }, 
        "display_name": "The Science of Happiness", 
        "end": "2014-11-29T00:00:00Z", 
        "enrollment_end": "2014-11-16T13:00:00Z", 
        "graceperiod": "", 
        "start": "2014-08-10T07:00:00Z", 
        "tabs": [
          {
            "name": "Courseware", 
            "type": "courseware"
          }, 
          {
            "name": "Course Info", 
            "type": "course_info"
          }, 
          {
            "name": "Discussion", 
            "type": "discussion"
          }, 
          {
            "name": "Syllabus", 
            "type": "static_tab", 
            "url_slug": "ecba5251441249b284dbdd58a5afb453"
          }, 
          {
            "name": "Progress", 
            "type": "progress"
          }, 
          {
            "name": "Wiki", 
            "type": "wiki"
          }
        ]
      }
    }, 




.. _Course Building Block Data:

**************************
Course Building Block Data
**************************

In a course outline, course teams organize course content into sections,
subsections, and units. Internally, the edX code identifies these building
blocks as chapters, sequentials, and verticals.

This example extracts the JSON documents that represent one of the sections in
a course, asubsection that it contains, and a unit that the subsection
contains.

======================================
Course Building Block Data Sample
======================================


.. code-block:: json

  "i4x://edX/DemoX/chapter/00d4374f346b4744aa6f4708cdf46d53": {
    "category": "chapter", 
    "children": [
      "i4x://edX/DemoX/sequential/9681154b9c0a4baaafb5f4e26bc71550"
    ], 
    "metadata": {
      "display_name": "Testing MOOCchat", 
      "start": "2020-08-09T16:00:00Z", 
      "visible_to_staff_only": true
    }
  }, 
  .
  .
  .
  "i4x://edX/DemoX/sequential/547f430ffd414a5fbb4a080fd5eb7566": {
    "category": "sequential", 
    "children": [
      "i4x://edX/DemoX/vertical/2ea89cbec5bd4034981a70abff7a82e1", 
      "i4x://edX/DemoX/vertical/7405431e9fe14354a39ac52a2973bc1c"
    ], 
    "metadata": {
      "display_name": "Why Does Happiness Matter?"
    }
  }, 
  .
  .
  .
   "i4x://edX/DemoX/vertical/7405431e9fe14354a39ac52a2973bc1c": {
    "category": "vertical", 
    "children": [
      "i4x://edX/DemoX/html/d3bd5215cf044056beb8e6f7f3e3afc4", 
      "i4x://edX/DemoX/video/ddf62dd7bff249efa1add6776f1e2ab8"
    ], 
    "metadata": {
      "display_name": "More on the Benefits of Happiness"
    }
  }, 
  .
  .
  .
  "i4x://edX/DemoX/vertical/778671e308e446409c0c797d9d424eae": {
    "category": "vertical", 
    "children": [
      "i4x://edX/DemoX/problem/db71da27320a44bdb45df31d0d801e20", 
      "i4x://edX/DemoX/discussion/05d808aad49543de997964be3bfac528"
    ], 
    "metadata": {
      "display_name": "Recap of Happiness Practice #1: Three Good Things"
    }



.. _Course Component Data:

*********************
Course Component Data
*********************


======================================
Course Component Data Sample
======================================



.. code-block:: json

  "i4x://edX/DemoX/html/d3bd5215cf044056beb8e6f7f3e3afc4": {
    "category": "html", 
    "children": [], 
    "metadata": {
      "display_name": "Intro to Video"
    }
  }, 
  .
  .
  .
  "i4x://edX/DemoX/video/ddf62dd7bff249efa1add6776f1e2ab8": {
    "category": "video", 
    "children": [], 
    "metadata": {
      "display_name": "More on the Benefits of Happiness", 
      "download_track": true, 
      "download_video": true, 
      "html5_sources": [
        "https://d2f1egay8yehza.cloudfront.net/BERGG101/BERGG101T314-V001800_100.mp4"
      ], 
      "sub": "BERGG101T314-V001800_100", 
      "youtube_id_1_0": "uxypPaUu8ng"
    }
  }, 
  .
  .
  .
    "i4x://edX/DemoX/problem/db71da27320a44bdb45df31d0d801e20": {
    "category": "problem", 
    "children": [], 
    "metadata": {
      "display_name": "Question #1 about Three Good Things", 
      "markdown": null, 
      "showanswer": "never", 
      "weight": 0.0
    }
  }, 
  .
  .
  .
  "i4x://edX/DemoX/discussion/05d808aad49543de997964be3bfac528": {
    "category": "discussion", 
    "children": [], 
    "metadata": {
      "discussion_category": "Week 2", 
      "discussion_id": "7be676c36bba4486aeeabe3ecb5b06e8", 
      "discussion_target": "How Did Three Good Things Affect You?", 
      "display_name": "Discussion"
    }
  }, 

the component types that you can choose:
discussion, html, problem, video


