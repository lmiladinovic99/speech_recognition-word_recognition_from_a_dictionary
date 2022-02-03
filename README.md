# Task description
Implement a tool that:
- It records through the words of the speaker, and for each of the words entered, it calculates the LPC and MFCC vectors.
- Allows you to set encoding parameters.
- Produces a report on the similarity of the words entered using DTW.

# Input
The user can enter any number of words through .wav files or using a microphone. Coefficients are calculated for all entered words and stored in memory.
When entering each new word, either through a .wav file or from a microphone, the tool should ask the user to name the word, for later display.

The tool must provide the following items at the input:
- Using a raw .wav file as input sound.
- Using the microphone as an input sound signal.
- There can be more than one word in the recording, with a minimum length of 3 seconds before and after each word. This silence should be cut before processing begins. The system should report an error message if it considers that there are no spoken words on the recording.
- Choice of Hamming, Hanning or none of the window functions.
- Select the width of the LPC window and the offset between two adjacent windows. Offer the user a choice between milliseconds or samples as units of measurement.
- Setting the parameter p for LPC encoding, ie. number of LPC coefficients.
- DFT window width selection for MFCC. Offer the user a choice between milliseconds or samples as units of measurement.
- Number of filters in MFCC encoding.
- Choice of whether Δ and ΔΔ coefficients are used or not. (described below)

Provide at least ten .wav files, with three test words each:
- Voice signal - male voice - 5 files.
- Voice signal - female voice - 5 files.
-Each record should have three different words within it, provided that:
  - Three male and three female records should have the same set of words (9 different words in the male voice, and the same 9 words in the female voice). Two male and two female speakers should be used for these test cases.
  - Two male and two female records should have completely different words (6 different words in the male voice, and 6 different words in the female voice).

# Output
After entering words, the user can calculate LPC or MFCC vectors for words. These vectors are stored under a new name, as the user may want to count multiple different representations for the same image.

After the user has been given vector word representations, he can choose:
- A collection of word representations that will serve as template bases.
- A representation of one word that will be tested on that base.

As a result of the search, the user should get how far the selected word is from each of the template databases, according to the DTW algorithm, as well as see the path within the DTW trellis for any of these searches.
