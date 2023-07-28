# NodeTree
Build a composite structure of nodes and their child nodes.

Here is the coding task :)


Assume there is a Node class:

import java.util.List;
import java.util.ArrayList;

public class Node {
private String data;
private List<Node> childNodes = new ArrayList<Node>();
// TODO: getter and setter for data and getter for child nodes
}

Using this class you can build the composite structure of nodes and their
child nodes.

Node root = new Node();
root.setData("root");
Node child0 = new Node();
child0.setData("child0 of root");
root.getChildNodes().add(child0);
//TODO: make the structure of nodes more complex

The goal of this task is to be able to store the nodes as:
1) XML file (two ways: a) using DOM with Xerces, b) using JAXB)
   <node data="root">
     <node data="child0 of root"/>
   </node>
2) records in RDBMS (you can use MySQL 5.1 or other choice of your own)
   (one way: a) using JDBC and SQL )
   ID     DATA     PARENT_NODE_ID
----    ----------------     ---------
1      root                <null>
2      child0 of root   1
3) RMI client and server for storing nodes and passing them over the wire

RESULTS
The solution should provide a NodeStorage interface with 4 major implementations

public interface NodeStorage {
Node read() throws NodeStorageException;
void store(Node node) throws NodeStorageException;
}

References:
1) for xerces DOM impl you can use this article
   http://totheriver.com/learn/xml/xmltutorial.html#6.2
2) for JAXB impl you can use this article
   http://www.mkyong.com/java/jaxb-hello-world-example/
3) for JDBC impl you can use this article
   http://www.vogella.com/articles/MySQLJava/article.html
4) for RMI impl you can use this article
   http://docs.oracle.com/javase/tutorial/rmi/index.html
