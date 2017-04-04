# wordsum-models

wordsum is a model and a tool to create the model. 

wordsum's goal is to model story and poetry, so a machine can read and learn story and poetry.
.
#### wordsum models
<table>
 <tr>
  <th>Model</th><th>State</th><th>Version</th>
 </tr>
 <tr>
  <th>Text Model</th><th>released</th><th>0.9.99</th>
 </tr>
 <tr>
  <th>Story Model</th><th>developing</th><th>0.1.0</th>
 </tr>
 <tr>
  <th>Metaphor Model</th><th>contemplating</th><th>0.0.0</th>
 </tr>
 <tr>
  <th>Poem Model</th><th>contemplating</th><th>0.0.0</th>
 </tr>
</table>

### Text Model

The Text Model models three states: the FileState, the ParagraphState and the SentenceState.

The FileState contains components to model the file containing the text data. It contains null or many ParagraphStates.

The ParagraphState contains components to model a paragraph. I contains one or many SentenceState states.

The SentenceState contains components to model a sentence.

Currently, only https://github.com/wordsum/wordsum-java outputs the Text Model.

#### FileState
<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>file</th><th>string</th><th>The absolute path to the digital file containing the text to be modelled.</th>
 </tr>
 <tr>
  <th>version</th><th>string</th><th>The model's version.</th>
 </tr>
 <tr>
  <th>sha</th><th>string</th><th>A unique identifier for the outputted modelled text.</th>
 </tr>
 <tr>
  <th>localDateTime</th><th>string</th><th>The time the modelled text was created.</th>
 </tr>
 <tr>
  <th>copyright</th><th>string</th><th>Any copyright covering the contents of the text model.</th>
 </tr>
 <tr>
  <th>writers</th><th>list of strings</th><th>A list of agents writing the modelled text in the file.</th>
 </tr>
 <tr>
  <th>editors</th><th>list of strings</th><th>A list of agents editing the modelled text in the file.</th>
 </tr>
 <tr>
  <th>publishers</th><th>list of strings</th><th>A list of agents publishing the modelled text.</th>
 </tr>
 <tr>
  <th>fileText</th><th>string</th><th>The text contents of the file.</th>
 </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>The amount of words in the entire file.</th>
 </tr>
 <tr>
  <th>paragraphStates</th><th>list of ParagraphStates</th><th>A list of ParagraphsStates found in the text file.</th>
 </tr>
</table>


#### ParagraphState


<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>paragraph</th><th>string</th><th>A string of the entire paragraph.</th>
 </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>The amount of words in the paragraph.</th>
 </tr>
 <tr>
  <th>order</th><th>integer</th><th>The order of the paragraph in a list of paragraphs.</th>
 </tr>
 <tr>
  <th>sentenceCount</th><th>integer</th><th>The amount of sentences in the paragraph.</th>
 </tr>
 <tr>
  <th>dialog</th><th>boolean</th><th>Is true if dialog exists in the paragraph.</th>
 </tr>
 <tr>
  <th>tense</th><th>list of strings</th><th>The list of tenses found in the paragraph.</th>
 </tr>
 <tr>
  <th>sentenceStates</th><th>list of SentenceStates</th><th>A list of all the SentenceStates found in the paragraph.</th>
 </tr>
</table>


#### SentenceState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>isCompleteSentence</th><th>boolean</th><th>A boolean to define if the string is actually a complete sentence and not a fragment.</th>
 </tr>
 <tr>
  <th>sentence</th><th>string</th><th>The string of sentences and all its punctuation.</th>
 </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>The amount of words in the sentence.</th>
 </tr>
 <tr>
  <th>orderParagraph</th><th>integer</th><th>Order of sentence in a paragraph with sentences.</th>
 </tr>
 <tr>
  <th>tense</th><th>list of string</th><th>A list of tenses found in the sentence.</th>
 </tr>
 <tr>
  <th>nlpState</th><th>NlpState</th><th>An object containing the NLP output of the sentence.</tr>
 </tr>
 <tr>
  <th>punctuationState</th><th>PunctuationState</th><th>An object containing the state of punctuation patterns found in the sentence.</tr>
 </tr>
 <tr>
  <th>spellcheckState</th><th>SpellcheckState</th><th>An object for both the words in the sentence not found in a dictionary along with an suggestions of other words.</tr>
 </tr>
 <tr>
  <th>dialogState</th><th>DialogState</th><th>A state defining the dialog state within the sentence.</tr>
 </tr>
</table>


#### Example Text Model output from wordsum-java

- **CharacterBuilderTest.txt** Production tested and verified story by placing in the first round of a writing contest, so it is seen by other humans of Pathfinder Chronicler as a complete story: http://pathfinderchronicler.net/baba-yaga-sneak-attack-by-kalab-j-oster/

-  **CharacterBuilderTest.json** wordsum-java output of CharacterBuilderTest.txt and used to verify production date with the wordsum feature for CharacterState and give example of the current revision of the wordsum model.

-  **SubjectVerbsObject.json** example test data for wordsum's character indicator builder for creating Character State of the story model.


### Story Model

The Story Model depends upon the Text Model to model its states of CharacterState, NarratorState, SettingState and PlotState.

As this model is more meta right now than Alpha,

Currently, only CharacterState is being written. Once the builder to create CharacterState exist then then NarratorState and SettingState will also be nearly complete.

PlotState is still a bit of mystery.



#### NarrativeState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>characterStates</th><th>An ordered list of CharacterStates.</th><th>An ordered list of states that defined the order or actions by a character during a narrative.</th>
 </tr>
 <tr>
  <th>narratorStates</th><th>An ordered list of NarratorStates.</th><th>An ordered list of states that define that narrators of a story whether it be different narrative voice telling the story of the narrator of character dialog.</th>
 </tr>
 <tr>
  <th>settingStates</th><th>An ordered list of SettingStates.</th><th>An ordered list of states that define the settings. </th>
 </tr>
 <tr>
  <th>plotStates</th><th>An ordered list of PlotStates.</th><th>A state of the plots throughout the story given all other states of NarrativeState are known.</th>
 </tr>
</table>

#### CharacterState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>name</th><th>string</th><th>The given or predicted name of the character.</th>
 </tr>
  <tr>
   <th>characterIndicators</th><th>A ordered list of character indicators</th><th>This list contains an ordered list of character indicators taken from the subject, verbs and objects of sentences from SentenceState.</th>
  </tr>
</table>

#### NarratorState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>Defining...</th><th>Defining...</th><th>Defining...</th>
 </tr>
</table>

#### SettingState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>Defining...</th><th>Defining...</th><th>Defining...</th>
 </tr>
</table>

#### PlotState

<table>
 <tr>
  <th>Component</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>Defining...</th><th>Defining...</th><th>Defining...</th>
 </tr>
</table>


## Copyright

  **Open Story License**

  **Story: wordsum-models**

  **Writer: Kalab J. Oster&trade;**

  **Copyright Holders: Kalab J. Oster&trade;**

  **copyright &copy; 2017 Kalab J. Oster&trade;**

  Permission is granted by the Copyright Holders for humans or other intelligent agents to read, write, edit, publish and critique the Story if the humans or intelligent agents keep this Open Story License with the Story, and if the Story remains free, and if another writer writes or edits the Story then the writer's name needs to be appended to the end of the Writer list of this Open Story License.

~


