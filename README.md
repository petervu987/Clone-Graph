# Clone-Graph

/*
// Definition for a Node.
class Node {
public:
    int val;
    vector<Node*> neighbors;
    Node() {
        val = 0;
        neighbors = vector<Node*>();
    }
    Node(int _val) {
        val = _val;
        neighbors = vector<Node*>();
    }
    Node(int _val, vector<Node*> _neighbors) {
        val = _val;
        neighbors = _neighbors;
    }
};
*/

class Solution {
public:
    unordered_map<Node*, Node*> m;

    Node* cloneGraph(Node* node) {
        if (node == nullptr) {
            return nullptr;
        }
        return whatever(node);
    }

    Node* whatever(Node* node) {
        if (m.count(node)) {
            return m[node];
        }

        Node* clone = new Node(node->val);
        m[node] = clone;

        for (Node* n : node->neighbors) {
            clone->neighbors.push_back(whatever(n));
        }
        return clone;
    }
};
