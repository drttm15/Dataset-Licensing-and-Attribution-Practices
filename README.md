Algorithm: HybridNet-Powered Dataset Licensing and Attribution Audit

Initialization
Load the RoBERTa model for text processing
Load the InceptionV3 model for visual content analysis
Set the threshold for anomaly detection and violation flagging
Data Collection and Preprocessing
	Input: Dataset metadata D_{meta} from OpenML
	For each dataset D_i\in\left\{D_1,D_2,\ldots,D_n\right\}:
		Retrieve the textual metadata X_{text}
		Retrieve the visual data X_{img}
		Preprocess and clean the data
License and Attribution Detection:
	Textual Analysis with RoBERTa:
		For each dataset D_i:
			Input the textual data X_{text}
			f_{text}=g_{RoBERTa}\left(X_{text}\right)			// Extract the textual feature vector
			y_{license}=\arg{\max{\left(h_{license}\left(f_{text}\right)\right)}}		// Classify the license type
			y_{attribution}=\arg{\max{\left(h_{attribution}\left(f_{text}\right)\right)}}	// Detect attribution requirements
	Visual Analysis with InceptionV3
		For each dataset D_i containing visual data:
			Input the visual data X_{img}
			f_{img}=g_{InceptionV3}\left(X_{img}\right)			// Extract the visual feature vector
			y_{vis_{attr}}=\arg{\max{\left(h_{vis_{attr}}\left(f_{img}\right)\right)}}		// Detect any visual attributions
	Final Attribution Classification
		y_{attr_{final}}=y_{attribution}\vee y_{vis_{attr}}		// Combine textual and visual attribution
Compliance Verification
		Cross Validation
			For each dataset D_i:
\delta_{license}=1        if ylicense≠Mlicense0        if ylicense=Mlicense 	// Compare the predicted license
\delta_{attribution}=1    if yattrfinal≠Mattribution0    if yattrfinal=Mattribution	// Compare the final attribution
Violation Identification
	\delta_{violation}=\delta_{license}\vee\delta_{attribution}			// Identify if any violations exist
	Flat D_i for review if \delta_{violation}=1
Reporting:
	For each dataset D_i:
		Generate a compliance report
		Display results
End Algorithm


Workflow of the Proposed HybridNet Framework

<img width="868" height="1216" alt="image" src="https://github.com/user-attachments/assets/c15de34a-38b5-4a4f-8bb0-052f7d97bd44" />

 

