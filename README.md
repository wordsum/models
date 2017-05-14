# wordsum-models

wordsum is a model and a tool to create the model. 

wordsum's goal is to model story and poetry for A.I..
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

The Text Model models three states: the File Model, the Paragraph Model and the Sentence Model.

The File Model models text to model a story to teach A.I..

The Paragraph Model models text of a paragraph to model a story to teach A.I..

The Sentence Model models text of a sentence to model a story to teach A.I..

https://github.com/wordsum/wordsum-java outputs the Text Model.

#### File Model
<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
  <tr>
   <th>fileText</th><th>string</th><th>fileText of type string is the text of the file.</th>
  </tr>
 <tr>
  <th>writers</th><th>list of strings</th><th>writers of type list of strings is a list of writers of the fileText.</th>
 </tr>
 <tr>
  <th>editors</th><th>list of strings</th><th>editors of type list of strings is a list of editors of the fileText.</th>
 </tr>
 <tr>
  <th>publishers</th><th>list of strings</th><th>publishers of type list of strings is a list of publishers of the fileText.</th>
 </tr>
  <tr>
   <th>copyright</th><th>string</th><th>copyright of type string is any copyright of the fileText.</th>
  </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>wordCount of type integer is the amount of words of the fileText.</th>
 </tr>
  <tr>
   <th>file</th><th>string</th><th>file of type string is the absolute path to the digital file of the fileText.</th>
  </tr>
   <tr>
    <th>version</th><th>string</th><th>version of type string is the version of the File Model.</th>
   </tr>
  <tr>
   <th>guid</th><th>string</th><th>guid of type string is a globally unique identifier for the File Model state.</th>
  </tr>
  <tr>
   <th>creationTime</th><th>string</th><th>creationTime of type string is the creation time of thee File Model state.</th>
  </tr>
 <tr>
  <th>paragraphStates</th><th>list of ParagraphStates</th><th>paragraphStates of type list of ParagraphStates is a list of Paragraph Model states of the File Model state</th>
 </tr>
</table>


#### Paragraph Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>paragraphText</th><th>string</th><th>paragraphText of type string is the text of the paragraph.</th>
 </tr>
 <tr>
  <th>order</th><th>integer</th><th>order of type integer is the ordinal placement of the paragraph of a File Model state.</th>
 </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>wordCount of type integer is the amount of words of the paragraphText.</th>
 </tr>
 <tr>
  <th>sentenceCount</th><th>integer</th><th>sentenceCount of type integer is the amount of sentences of the paragraphText.</th>
 </tr>
 <tr>
  <th>dialog</th><th>boolean</th><th>dialog of type boolean is of the paragraphText.</th>
 </tr>
 <tr>
  <th>tense</th><th>list of strings</th><th>tense of type list of strings is a list of tenses of the paragraphText.</th>
 </tr>
 <tr>
  <th>sentenceStates</th><th>list of SentenceStates</th><th>sentenceStates of type list of SentenceStates is a list of Sentence Model states of the Paragraph Model state.</th>
 </tr>
</table>


#### Sentence Model


<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>sentenceText</th><th>boolean</th><th>sentenceText of type string is the text of the sentence.</th>
 </tr>
 <tr>
  <th>order</th><th>integer</th><th>order of type integer is the ordinal placement of the sentence of the Paragraph Model state.</th>
 </tr>
 <tr>
  <th>wordCount</th><th>integer</th><th>wordCount of type integer is the amount of words of the sentenceText.</th>
 </tr>
 <tr>
  <th>tense</th><th>list of strings</th><th>tense of type list of strings is a list of tenses of the sentenceText.</th>
 </tr>
 <tr>
  <th>nlpState</th><th>NlpState</th><th>nlpState of type NlpState is an Natural Language Processing Model state of the sentenceText.</tr>
 </tr>
 <tr>
  <th>punctuationState</th><th>PunctuationState</th><th>punctuationState of type PunctuationState is a Punctuation Model state of the sentenceText.</tr>
 </tr>
 <tr>
  <th>spellcheckState</th><th>SpellcheckState</th><th>spellcheckState of type SpellcheckState is a Spellcheck Model state of the sentenceText.</tr>
 </tr>
 <tr>
  <th>dialogState</th><th>DialogState</th><th>dialogState of type DialogState is a Dialog Model state of the sentenceText.</tr>
 </tr>
</table>


#### Example Text Model output from wordsum-java

- **CharacterBuilderTest.txt** Production tested and verified story by placing in the first round of a writing contest, so it is seen by other humans of Pathfinder Chronicler as a complete story: http://pathfinderchronicler.net/baba-yaga-sneak-attack-by-kalab-j-oster/

-  **CharacterBuilderTest.json** wordsum-java output of CharacterBuilderTest.txt and used to verify production date with the wordsum feature for CharacterState and give example of the current revision of the wordsum model.

-  **SubjectVerbsObject.json** example test data for wordsum's character indicator builder for creating Character State of the story model.


### Story Model

The Story Model models the states: Narrative Model, Character Model, Narrator Model, Setting Model and Plot Model.


#### Narrative Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
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

#### Character Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>name</th><th>string</th><th>The given or predicted name of the character.</th>
 </tr>
  <tr>
   <th>characterIndicators</th><th>A ordered list of character indicators</th><th>This list contains an ordered list of character indicators taken from the subject, verbs and objects of sentences from SentenceState.</th>
  </tr>
</table>

#### Narrator Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>Defining...</th><th>Defining...</th><th>Defining...</th>
 </tr>
</table>

#### Setting Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
 </tr>
 <tr>
  <th>Defining...</th><th>Defining...</th><th>Defining...</th>
 </tr>
</table>

#### Plot Model

<table>
 <tr>
  <th>Feature</th><th>Type</th><th>Purpose</th>
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


