# study-notes
Computer science study notes

# Binary Search

```java
int binarySearch(int[] array, int value) {
    int start = 0;
    int end = array.length - 1;

    while (start <= end) {
        int m = (start + end) / 2;
        if (array[m] == value)
            return m;
        else if (array[m] < value)
            left = m + 1;
        else
            right = m - 1;
    }

    return -1;
}
```

# Binary Search Tree

```java
class Node {
    int value;
    Node left;
    Node right;

    Node(int value) {
        this.value = value;
        this.left = null;
        this.right = null;
    }
}

class BinarySearchTree {
    Node root;

    Node search(int value) {
        Node node = root;

        while (node != null) {
            if (node.value == value)
                return node;
            else if (node.value > value)
                node = node.left;
            else
                node = node.right;
        }

        return node;
    }

    void traverse(Node node) {
        if (node.left != null)
            traverse(node.left);

        processNode(node); // calls to this function will be in sorted order

        if (node.right != null)
            traverse(node.right);
    }
```

# Graph

```java
class Node {
    int value;

    Node(int value) {
        this.value = value;
    }
}

class Graph {
    Map<Node, List<Node>> adjacentNodes;
}
```

# Depth-first search (DFS)

```java
Node dfs(Graph graph, Node root, int value) {
    Set<Node> visited = new HashSet<>();
    Stack<Node> stack = new Stack<>();

    stack.push(root);

    while (!stack.isEmpty()) {
        Node node = stack.pop();

        if (!visited.contains(node)) {
            visited.add(node);

            if (node.value == value)
                return node;
            else
                for (Node adjacentNode : graph.adjacentNodes.get(adjacentNodes))
                    stack.push(adjacentNode);
        }
        
    }

    return null;
}
```

# Breadth-first search (BFS)

```java
Node bfs(Graph graph, Node root, int value) {
    Set<Node> visited = new HashSet<>();
    Queue<Node> queue = new LinkedList<>();

    queue.add(root);

    while (!queue.isEmpty()) {
        Node node = queue.remove();

        if (!visited.contains(node)) {
            visited.add(node);

            if (node.value == value)
                return node;
            else
                for (Node adjacentNode : graph.adjacentNodes.get(adjacentNodes))
                    queue.add(adjacentNode);    
        }
    }

    return null;
}
```
