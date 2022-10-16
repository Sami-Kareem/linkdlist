# linkdlist
all beginners methods   


class Node1 {


    Node1 head;
    Node1 next;
    int data;
    int size = 0;

    public Node1() {
        //this.data = data;
        this.next = null;
    }
    public void addAtFirst(int data){
        Node1 newNode = new Node1();
        newNode.data = data;
        if (head == null){
            head = newNode;
            newNode.next = null;
            size++;
        }
        else {
            newNode.next = head;
            head = newNode;
            size++;

        }
    }

    public void addAtLast(int data){
        Node1 newNode = new Node1();
        newNode.data = data;
        if (head == null){
            head = newNode;
            newNode.next = null;
            size++;
        }
        else {
            Node1 curr = head;
            while (curr.next != null){
                curr = curr.next;
            }
            curr.next = newNode;
            newNode.next = null;
            size++;
        }
    }

    public void addAtIndex(int data, int index){

        Node1 newNode = new Node1();
        newNode.data = data;
        if (index == 1){
            addAtFirst(data);

        }
        else if(index == size+1){
            addAtLast(data);


        }
        else if(index > 1 && index <= size ) {
            Node1 curr = head;
            Node1 Fastcurr = head;
            for (int i = 2; i <= index; i++){

                Fastcurr = Fastcurr.next;
                if (i== index-1){
                    curr.next = newNode;
                    newNode.next = Fastcurr;
                    size++;
                    break;
                }
                curr = curr.next;
            }
        }
        else System.out.println("Size of list is: from 1 to "+size+", so no change in the list. ");

    }

    public void deleteAtFirst(int index){

        if (index == 1){
            head = head.next;
            size--;
        }
    }


    public void deleteAtLast(){


            Node1 cur =head;
            for (int i =1; i < size; i++){
                if ( i == size-1){
                    cur.next = null;

                    size--;

                    break;
                }
                cur = cur.next;
            }

    }

    public void printList(){
        Node1 curr = head;
        System.out.println("LinkedList with size "+size+" is: ");
        while (curr != null){
            System.out.println(curr.data+" -> ");
            curr = curr.next;
        }
       // System.out.println("null");

    }


}

class LL
{
    public static void main(String sami[]){
        Node1 n = new Node1();

        n.addAtLast(6);
        n.addAtLast(8);
        n.addAtLast(9);
        n.addAtLast(10);
        n.addAtLast(11);
        n.addAtLast(12);
        n.addAtIndex(7,7);

        n.deleteAtLast();

        n.printList();
    }

}
