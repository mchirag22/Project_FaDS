Version Summary

v0.1_HFD_using_dlib_FFD;
    Goal: To figure out if dlib can be used to detect human faces reliably.
    Result: dilib is a piece of crap and should never be used for something like this if accuracy at any level is needed.
    Observations;
        1. Easy to setup, easy to run.
        2. Very slow, as it doesn't use GPU processing.
        3. Human face detection accuracy is not reliably good.
        4. Fails to detect faces from all angles, sometimes detects faces in non-human objects.
        5. Can't be fine-tuned.


v0.2_HFD_using_yolov8;
    Goal: To figure out if yolov8 fine-tuned for human faces, can be used to detect human faces reliably.
    Result: yolov8n-face worked way better than expected and is accurate enough for normal usage.
    Observations;
        1. Slightly technical to setup, easy to run.
        2. Way faster than dlib, but can do way better as I'm still not able to use GPU with it.
        3. Human face detection accuracy is way better than expected. This is leaps and bounds ahead of dlib.
        4. Detects faces from most of the angles, exposures, and focus levels, there were very few cases where it detected non human objects as human faces but the confidence level there was less than 50%.
        5. The model is already fine tuned for human faces, and can still further be fine tuned if needed.

v0.3_Face_Embedding_using_Facenet
    Goal: To figure out if Facenet can work with the faces detected by yolov8n-face and convert those into embedding that can later be used for clustering or indexing.
    Result: Facenet performed seamlesly and was pretty quick to create face embeddings.
        Observations;
        1. Easy to setup, easy to run.
        2. Facenet model is pretty fast and accurate for the usecase.
        3. Still need to figure out how to use GPU with it.