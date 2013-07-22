Swap-Nodes-in-Pairs
===================
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode swapPairs(ListNode head) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        if(head == null) return null;
        
        ListNode helper = new ListNode(0);
        helper.next = head;
        
        ListNode newhead = new ListNode(1);
        
        if(head.next!=null){
        newhead = head.next;
        }
        
        else{
            newhead = head;
        }
        
        ListNode n2 = head;
        ListNode n1 = helper;
        
        while(n2!=null && n2.next!=null){
            ListNode temp = n2.next.next;
            n2.next.next = n2;
            n1.next = n2.next;
            n2.next = temp;
            n1 = n2;
            n2 = n2.next;
        }
        
        return newhead;
        
    }
}
