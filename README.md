COMP8420 Major Project

Creo Baylon
Student No: 48288209
creo.baylon@students.mq.edu.au

Neeladri Bhowmik
Student No: 48191523
neeladri.bhowmik@students.mq.edu.au

_______________________________________________________________________________________________________________

MAIN FILES
_______________________________________________________________________________________________________________

The dataset is stored in Prompts.csv. It has two columns:
1) "Prompts" contains the rambling prompts
2) "Short" contains the shortened version of the prompts as done by the LLM.

TrainingCode.py is how the LLM's response was generated ("Short" Column)
 
The main code in this project is AdversarialTraining.py.

AdversarialTraining.py references 3 other Codes:

1) GeneratorCode.py is where the class object for the Generator structure.
2) DiscriminatorCode.py is where the pre-trained discriminator and the custom discriminator class objects are.
3) DataSetObject.py is where the Dataset Object class object is.

AdversarialTraining also creates the following files:

1) GATTDAMGeneratorADV.pth contains the weights of the final Generator Model
2) GATTDAMGeneratorSV.pth contains the weights of the Generator Model before adversarial training but after supervised training
3) Prompts_With_Generated.csv is a version of the Prompts.csv with the Generator's response set as column "Generated". 
4) adv_loss_curve.png and disc_acc_curve.png contain the graphs of generator loss per epoch and discriminator accuracy per epoch respectively. 
5) TestQuestionnaire.csv and TrainQuestionnaire.csv contain 193 data samples each, with the response of the LLM and the Generator set as the "LLM" and "Generated" columns respectively.

The questionnaires are checked manually to produce data on training vs testing.


FOLDERS
_______________________________________________________________________________________________________________

The file folders contain all the files that the AdversarialTraining.py file produces, as well as two other files:

1) PreliminaryChecker.py makes human checking more efficient, by immediately counting the Generator's response as "acceptable" if it is a direct copy of the LLM's response, by labelling it as "1". This in the "Check" Column.
2) SavingsCalculator.py is used to calculate what percent of tokens the Generator and the LLM saves. This is used for both training and testing questionnaires.

The folder "200 Epochs" up to "500 Epochs" contains the relevant files for fully hybrid adversarial training for Phase 2.

The folder "1000 Epochs" contains the relevant files for 275 epoch hybrid training followed by 725 epochs of pure adversarial training for Phase 3.

The folder "CustomTransformer" contains the relevant files for 300 epochs of hybrid training using a custom transformer for Phase 4.


RECORD FILES
______________________________________________________________________________________________________________

Results.txt contains the data needed to create the graph shown in Phase 2. (Training and Testing performance per epoch)
TrainingLog.txt is a remenant file from Phase 1: This was where the generator output was monitored for preliminary testing.
Phase2Graph is the code that uses the data recorded in Results.txt to produce the Phase 2 Graph.
