# Data-Structures-by-Ali
package com.company;

public class doublyLinkedList<anytype>{

    anytype data;
    Node head,tail;

    public doublyLinkedList() {
        this.data = data;
        this.head = head;
        this.tail = tail;
    }

    //private class
    private class Node {

        anytype data;
        Node next, prev;

        public Node(anytype data, Node next, Node prev) {
            this.data = data;
            this.next = next;
            this.prev = prev;
        }
    }

    public void addFirst(anytype data){
        if (head==null){
            Node temp = new Node(data, null,null);
            head = temp;
            tail = temp;
        }
        else{
              Node temp = new Node(data,head,null);
              head.prev = temp;
              head = temp;
        }
    }

    public void addLast(anytype data){
        if (head==null){
            addFirst(data);

        }
        else{
            Node temp = new Node(data,null,tail);
            tail.next=temp;
            tail = temp;
        }

    }


    //display data forward
    public void displayforward(){
       Node temp = head;
       if(temp==null){
           System.out.println("No list");
       }
       else{
           while (temp!=null){
               System.out.print(temp.data+",");
               temp = temp.next;
           }
       }
    }


    //display data backward
    public void displaybackward(){
        Node temp = tail;
       // int count = 0;
        if(temp==null){
            System.out.println("No list");
        }
        else{
            while (temp!=null){


                System.out.print(temp.data+",");
                temp = temp.prev;            }
        }
    }

     public boolean isEmpty() {

        if (head == null)
             return true;

           else {
               return false;
         }
     }

     //search index node
    public int search(anytype data){
        int count = -1;
        Node temp = head;

        if (temp==null)
            return -1;

        while(temp!=null){
            if (temp.data==data){
                count++;
                return count;
            }
            else{
                count++;
                temp = temp.next;
            }
        }
        return -1;
    }

    //delete first
    public void deleteFirst(){
        Node temp = head;
        if (temp == null){
            System.out.println("no list for deletion");
        }
        else{
            temp=temp.next;
            head=temp;
            head.prev=null;
        }
    }

//delete last delete
    public void deleteLast(){
        Node temp = tail;
        if (temp == null){
            System.out.println("no list");
        }
        else{
            temp = temp.prev;
            tail = temp;
            tail.next = null;
        }
    }

    public static void main(String[] args) {
	// write your code here
        doublyLinkedList<String> obj = new doublyLinkedList<String>();
               obj.addFirst("ali");
               obj.addLast("khan");
               obj.addLast("magsi");

               obj.deleteLast();
       // System.out.println("index is : "+obj.search("khan"));
        obj.displayforward();
    }
}
