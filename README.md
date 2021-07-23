# Head-Matters--Code
Preprocessing -- We've used openface(https://github.com/TadasBaltrusaitis/OpenFace) to extract pose angles anad action units for kineme and AU generation.

Model Architecture -- We've done Chunk level and video level analysis for both the datasets MIT and FICS. For more details, please refer to paper.

Types of architecture -- 
<ol>
  <li> Decision fusion -- We are considering two LSTM model for AU_Only and kineme_Only. After taking teh scores from each model, we've implemented the following formula to find the DF score.
  <br>
  <b>DF_score = w*Kineme_only_score + (1-w)*AU_only_score</b>
  <br>
    w is a weight parameter between 0 and 1. We've considered it with step size 0.05 </li>
    
  <li> Feature fusion (Merged architecture) -- Kindly refer the following figure.
 
  https://github.com/MonikaGahalawat11/Head-Matters--Code/blob/main/Merged_architecture.png
  
  </li>
 </ol>
 <br>
List of parameters:
<ol>
  <li> nKineme contains the number of kinemes clusters created (its a user defined parameter-- in our case it's 16) </li>
  <li> seqLen defines the length/size of each chunk (seqLen for the datasets varies as per chunk size) </li>
  <li> nAction is the size of vector for action units; as we extract 17 action units from openface </li>
  </ol>
  
To Run the Regression Code, access the Folder "Data_For_Regression". All the needed sample data to run regression code is available in the Folder "Data_For_Regression" .
