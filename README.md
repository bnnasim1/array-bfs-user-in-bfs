# array-bfs-user-in-bfs

package algo_bfs;

import java.util.Scanner;
import java.util.LinkedList;
import java.util.Queue;

class BFS 
{

    BFS() 
    {
        ST(); 
    }

    void ST()
    {
        int m, n,i,j;
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the number of rows: ");

        m = sc.nextInt();
        System.out.print("Enter the number of columns: ");
 
        n = sc.nextInt();
  
        int graph[][] = new int[m][n];
   
        System.out.println("Enter the elements of the array: ");
 
        for (i = 0; i < m; i++)   
        {
            for (j = 0; j < n; j++) {
                graph[i][j] = sc.nextInt();
            }
        }
   
        System.out.println("Elements of the array are: ");
        for (i = 0; i < m; i++) {
            for (j = 0; j < n; j++)  
            {
                System.out.print(graph[i][j] + " ");
            }
  
            System.out.println();
        };
        int vis[], lev[]; // visited and level array
        
        vis = new int[m];
        lev = new int[m];

        for (int k = 0; k < m; i++) // initialize the visited and level array
        {
            vis[k] = 0; // white
            lev[k] = 999999; // infinite
        }
        int s = 0; // source node
        vis[s] = 1; // gray
        lev[s] = 0;

        Queue<Integer> q = new LinkedList<>();
        q.add(s);

        while (!q.isEmpty()) {
            int u = q.poll(); // this will work as parent node
            for (int v = 0; v < m; v++) {
                if (graph[u][v] == 1 && vis[v] == 0) // visit the child nodes v
                {
                    vis[v] = 1;
                    lev[v] = lev[u] + 1;
                    q.add(v);
                }
            }
            vis[u] = 2;
        }
        for (int k = 0; k < m; k++) {
            System.out.println("Node = " + k + " Level = " + lev[k]);
        }
    }
}

    public class Algo_BFS 
    {

    public static void main(String[] args) {
        

            BFS b = new BFS();
        }
    
}
   
