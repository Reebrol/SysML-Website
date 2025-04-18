# Introduction
As indicated by the name, sequence diagrams are meant to describe and document the temporal operation of a system. The diagram is meant to visually explain structural and functional aspects of systems that rely on message passing between objects  such as object oriented and distributed systems.
# The Guidelines
## Sequence Layout
### Ordering Sequences
Sequences should follow a left-to-right, top-to-bottom arrangement. This sequence is not always strictly possible since some objects communicate bidirectionally or asynchronously across their lifespans.
### Lifeline Layers
The vertical position of the lifelines can be offset to indicate system layers. The system layers indicate both physical and logical arrangements of related lifelines and can make the grouping of related lifelines more apparent.
### Use Prose Descriptions
A common issue with Sequence diagrams is that sometimes the overarching purpose of the process or workflow is lost in the details of specific objects passing messages which sometimes includes loops or asynchronous processing. Adding a descriptive prose outline on the left hand side of the diagram is useful to clarify the subprocess that is being illustrated (c.f. Ambler (2005) fig. 30)
### Place Initiators on the Left
The process or object that initiates communication should be placed to the left of the receiver.
### Place Reactors/Receivers on the Right
The process or object that receives communication should be placed to the right of the initiator.
### Avoid Activation Boxes
Use activation boxes sparingly. If it is important for the audience of the diagram to consider processing time then indicating the active and inactive portions of each lifeline is OK. However, if it does not bring clarity they may be omitted. The more important feature to highlight is the sequence and direction of message passing. Thus arrange the diagram in a way that makes the timing of  the sending and receipt of these messages clear.
### Use Consistent Stereotypes
 Labels for lifelines are only weakly standardized and mostly uses by convention. Be sure to label objects consistently. Make sure to distinguish between real-world actors and classes that represent those actors.
### General Layout Considerations
Including an explicit depiction of object lifecycles such as object destruction or other explicit resource management can introduce clutter in the diagrams without adding clarity to the presentation of the sequence of actions and data flows. Avoid these especially when the target implementation language does not rely on explicit destruction (e.g. garbage collected or managed code).

In addition to the best practices discussed here, certain publication requirements may need to be accommodated depending on the medium of publication or organizational standards. Additional additional formatting can be made compliant as follows.
#### Headers and Footers
The diagram should be able to accommodate headers and footers.  The text of the headers and footers should be centered. The color and size of the footer should be configurable to comply with external publication requirements.
#### Left & Right Margins
The left margin should be reserved for additional explanatory notes & references about each particular diagram.

The right margin should be reserved for a "Legend" or "Key" that explains the semantics of any custom fonts, font weights, or colors used in each particular diagram. 

## Lifelines

### Naming Guidelines
Lifelines should have descriptive names that match the type of the objects they model. Use stereotypes as needed to clarify object types and avoid naming collisions as possible.
### Layout Guidelines
As before, the recommended layout across the diagram is to arrange lifelines that start their activities earlier further to the left and proceed rightward. The temporal sequence within each lifeline proceeds top to bottom.
## Messages

### Types of Messages
Messages can represent physical actions by human users, function calls (local or remote), network messages, or inter-process communications. Thus the specific syntax of the message shown will vary.  Preferentially use prose descriptions when describing human actions and pseudocode when describing data exchange initiated and received by software or hardware devices.
### Representing Object Lifecycles
Explicit object creation and destruction should only be used when it makes the model clearer. In most cases, diagramming object destruction is unnecessary. However, showing the precise timing of object creation can be helpful and is indicated using the `<<create>>` stereotype.
### Stereotypes
Some messages can refer back to use cases via the use of the `<<include>>` stereotype.
### Further Layout Considerations
Messages should be justified towards the arrowhead on the arrows in diagram.

## Return Values

### When to include Return Values
Return values are indicated by dashed arrows and should only be included when it is ambiguous what the type or value of the object being returned will be. 
### Types as Return Values
Return values can be simply the type of object being returned but if the specific return value is the salient element in deciding the next actions for the message receiver, return values can be listed as well.
### Layout Considerations & Formatting
The return value should be justified towards the arrowhead on the arrows in diagram.
# Conclusion

Sequence diagrams represent an intermediate stage in design. They display more implementation details than Use Cases and are closer to the actual code. However, while they are useful in the design of message passing systems, such as multi-tier distributed systems, they are not suited for displaying complex branched logic or algorithms. These design elements are better left to State Diagrams and Activity Diagrams that are equipped to visualize those elements of data processing. 

# References
\[1] The Elements of UML Style
\[2] How consistency is handled in model‑driven software engineering and UML: an expert opinion survey Software Quality Journal (2023) 31:1–54 https://doi.org/10.1007/s11219-022-09585-2
\[3] OMG Systems Modeling Language (OMG SysML™) Tutorial (September, 2009)
\[4] SYSML V2: Where We Are and How We Got Here (OMG Meeting Orlando, FL June 21, 2023)