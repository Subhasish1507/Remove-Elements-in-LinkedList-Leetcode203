# Remove-Elements-in-LinkedList-Leetcode203
This DSA question is given in leetcode 203 and  i solved this question using java language.

import java.util.Scanner;
class Remove{
    public static class ListNode
    {
        int val;
        ListNode next;
        ListNode(){}
        ListNode(int val)
        {
            this.val = val;
        }
        ListNode(int val,ListNode next)
        {
            this.next = next;
            this.val = val;
        }
    }
    public ListNode removeElements(ListNode head,int val)
    {
        ListNode dummy = new ListNode(-1);
        dummy.next = head;
        ListNode curr = dummy;
        while(curr.next!=null)
        {
            if(curr.next.val==val)
            {
                curr.next = curr.next.next;
            }
            else
            {
                curr = curr.next;
            }
        }
        return dummy.next;
    }
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Remove remove = new Remove();
        System.out.print("Enter the Linked List elements (only 6 elements ):");
        ListNode head = new ListNode(input.nextInt());
        ListNode l1 = new ListNode(input.nextInt());
        ListNode l2 = new ListNode(input.nextInt());
        ListNode l3 = new ListNode(input.nextInt());
        ListNode l4 = new ListNode(input.nextInt());
        ListNode l5 = new ListNode(input.nextInt(),null);
        head.next = l1;
        l1.next = l2;
        l2.next = l3;
        l3.next = l4;
        l4.next = l5;
        ListNode ptr = head;
        System.out.println("The Linked List in diagrmatic form is : ");
        while(ptr != null)
        {
            System.out.print(ptr.val+"->");
            ptr = ptr.next;
        }
        System.out.println("null");
        System.out.print("Enter the element to be delete : ");
        head = remove.removeElements(head, input.nextInt());
        System.out.println("Finally Linked List in diagrmatic form is : ");
        ptr = head;
        while(ptr != null)
        {
            System.out.print(ptr.val+"->");
            ptr = ptr.next;
        }
        System.out.println("null");
    }
    
}
