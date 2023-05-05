Download Link: https://assignmentchef.com/product/solved-cse522-assignment-1-define-abstree-deleten
<br>
<h1>PART 1:   Define AbsTree.delete(n)</h1>

Lecture 3 slides 37-43 present an object-oriented definition of a binary search tree called class AbsTree, with two subclasses, Tree and DupTree.  In this part of the assignment, you are to complete the definition of the delete operation in class AbsTree in such a way that it works for both trees and duptrees.    The method delete(int n) should ensure that, if n is removed from a tree or duptree,  the remaining values maintain the binary search tree property.  For duptrees, the removal of n from the duptree takes place only when its associated count is 1.

Posted at Resources → Assignments → AbsTree_with_delete.java is starter code for Part 1.  You are to extend this code in order develop your solution.

<strong><em>Preliminaries</em>:</strong>  In order to facilitate a simpler solution for delete, a protected field AbsTree parent is added to class AbsTree.   Revise the insert method so that the parent field is correctly set when a value is inserted into a tree or duptree.

Define three procedures, min(), max(), and find(n) which return, respectively, the AbsTree node with the minimum value, the AbsTree node with the maximum value, and the AbsTree node containing the value n.  If n is not present in the tree, find(n) should return null.

Similar to insert, the code for delete should be factored and kept entirely in class AbsTree and captures what is common to trees and duptrees.   The differences in delete’s behavior between Tree and DupTree are expressed in terms of two simple protected abstract methods, called get_count() and set_count(int n), with obvious meanings.  You should implement these two methods in classes Tree and DupTree.

<strong><em>Definition of delete</em>:  </strong> A good explanation of delete is given at:

http://www.algolist.net/Data_structures/Binary_search_tree/Removal

There are four main cases to delete depending upon whether the value to be deleted is at:

<ul>

 <li>A leaf node (but not the root); or</li>

 <li>A non-leaf node (but not the root) with only one non-null subtree; or (iii)  A root node with one non-null subtree; or (iv)  A node with both non-null subtrees.</li>

</ul>

FYI: A leaf node has the property that left == null and also right == null.

Note that we do not allow the root node to be deleted if it has both null subtrees.  Also,  when a value n in a duptree has a count &gt; 1, the method delete(n) should decrement the count field associated with n but should not delete the node. If a value n is associated with a count == 1, the method delete(n) should remove the node containing value n from the duptree.

Two screen-casts A1_Part1_Tree_delete.mp4 and A1_Part1_DupTree_delete.mp4will also be posted to clarify delete’s behavior for the given test cases.

<strong><em>Starter Code</em></strong>: The code for the top-level definition of delete in class AbsTree has been provided to you – do not modify this definition.  The method makes use of four helper methods, called case1, case2, case3L, and case3R.  The methods case1 and case2 correspond to cases (i) and (ii) described above while case (iii) is implemented using two methods, called case3L and case3R, depending upon whether the missing tree is on the left (case3R) or the right (case3L). Case (iv) can be handled using case3L or case3R – the starter code given to you makes use of case3R.

<strong><em>JIVE Diagrams:</em></strong> The file AbsTree_with_delete.java provides two tester classes:  Tree_Test, for testing trees, and DupTree_Test,  for testing duptrees.  Run both test cases to completion under JIVE, and save the diagrams in files called A1_Tree_obj.png and A1_Tree_seq.png for object and sequence diagrams for trees; and A1_DupTree_obj.png and A1_DupTree_seq.png for object and sequence diagrams for duptrees, respectively.  Choose the “Objects with Tables” option for the Object Diagrams.

<h1>Part 2:  Transform Inheritance in terms of Delegation</h1>

<strong> </strong>

An important technique in the study of Object-Oriented Design is the use of <em>delegation</em> to replace <em>class inheritance</em>.   A systematic approach for this transformation was presented in Lectures 4 and 5.   Apply this approach to the program Resources → Assignments → Delegation.java.  This program defines classes A, B, C, D, E, and F.  The result of your transformation should be definition of classes called A2, B2, C2, D2, E2, and F2 which correspond to classes A, B, C, D, E, and F respectively, but do not make use of class inheritance.   The original program and the transformed program, when executed, should produce the same results for the given test cases.




A systematic approach involves the following steps:




<ol>

 <li>Define an interface hierarchy with interfaces IA, IB, IC, ID, IE, and IF based upon classes A, B, C, D, E, and F. (Optimize the interfaces to avoid redundancy.)</li>

 <li>Define new classes A2, B2, C2, D2, E2, and F2 which implement IA, IB, IC, ID, IE, and IF</li>

 <li>Set up the delegation hierarchy, define delegation methods, and provide a translation for every protected abstract method.</li>

 <li>Introduce one more default methods in the interfaces so that the number of delegation methods are minimized.</li>

 <li>Translate the pseudo-variables this and super as this2 and super2 respectively.</li>

 <li>Non-static-final attributes should be accessed by ‘super2-chaining’. Public static final attributes should be declared in interfaces.</li>

 <li>In the translated program, you will also need to define two constructors for every non-leaf non-abstract class of the original class hierarchy, i.e., for classes B2 and D2.</li>

</ol>




The file Delegation.java contains the definitions of classes A … F and also contains two tester classes called Delegation and Delegation2.  It also contains the outline of the classes A2 … F2.   Define the interfaces IA … IF and the classes A2 … F2 in the same file.




Run both test cases through JIVE and save the object and sequence diagrams in files named

A1_Delegation_obj.png and A1_Delegation_seq.png (for the first test case) and

A1_Delegation2_obj.png and A1_Delegation2_seq.png (for the second test case).    For object diagrams, choose ‘Objects with Tables’.  For sequence diagrams, choose ‘Expand Lifelines’.


