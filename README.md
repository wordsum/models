# wordsum

wordsum is a model and a tool to create the model. 

wordsum's goal is to model story and poetry, so a machine can read and learn story and poetry.
.

<table>
 <caption>wordsum models</caption>
 <tr>
  <th>model</th><th>state</th><th>version</th>
 </tr>
 <tr>
  <th>text model</th><th>released</th><th>0.9.99</th>
 </tr>
 <tr>
  <th>story model</th><th>developing</th><th>0.1.0</th>
 </tr>
 <tr>
  <th>metaphor model</th><th>contemplating</th><th>0.0.0</th>
 </tr>
 <tr>
  <th>poem model</th><th>contemplating</th><th>0.0.0</th>
 </tr>
</table>

### Text Model

The text model consist of three nested models. The file state model, the paragraph state model and the sentence state model. As defined following these words, the sentence state is the most discrete model while the paragraph state models paragraphs and consists of sentence states. The file state models contains file data along with paragraph states modelled.


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
  <th>paragraphStates</th><th>list of paragraph states</th><th>A list of modelled paragraphs states found in the text file.</th>
 </tr>
</table>





### Example Output from wordsum-java

- **CharacterBuilderTest.txt** Production tested and verified story by placing in the first round of a writing contest, so it is seen by other humans of Pathfinder Chronicler as a complete story: http://pathfinderchronicler.net/baba-yaga-sneak-attack-by-kalab-j-oster/

-  **CharacterBuilderTest.json** wordsum-java output of CharacterBuilderTest.txt and used to verify production date with the wordsum feature for CharacterState and give example of the current revision of the wordsum model.

-  **SubjectVerbsObject.json** example test data for wordsum's character indicator builder for creating Character State of the story model.
