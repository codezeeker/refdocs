Ref CARDS - flash cards
----------------------

SOLID principles--
S
O
L - Liskov sub principle - Every subclass shud be substituable for their parent class
I
D



Abstract Factory pattern deals with multiple families of products.


OAuth is an - authorization framework
grant type -     client credentials     - making API req for own account
                Authorization code     - making API req for another user's accont
                Implicit             - common for javascript
              
              
- cleaning inbox is may be look productive - but u actually not accomplished/produced anything 
 
 
 Stateless object is an instance of a class without instance fields (instance variables). The class may have fields, but they are compile-time constants (static final).

A very much related term is immutable. Immutable objects may have state, but it does not change when a method is invoked (method invocations do not assign new values to fields). These objects are also thread-safe.



 Weak HashMap
 -------------------------------------
  Map hashMap= new HashMap();
            Map weakHashMap = new WeakHashMap();

            String keyHashMap = new String("keyHashMap");
            String keyWeakHashMap = new String("keyWeakHashMap");

            hashMap.put(keyHashMap, "helloHash");
            weakHashMap.put(keyWeakHashMap, "helloWeakHash");
            System.out.println("Before: hash map value:"+hashMap.get("keyHashMap")+" and weak hash map value:"+weakHashMap.get("keyWeakHashMap"));

            keyHashMap = null;
            keyWeakHashMap = null;

            System.gc();  

            System.out.println("After: hash map value:"+hashMap.get("keyHashMap")+" and weak hash map value:"+weakHashMap.get("keyWeakHashMap"));
            
            
            output:
            Before: hash map value:helloHash and weak hash map value:helloWeakHash
            After: hash map value:helloHash and weak hash map value:null
 ---------------------------------------
 
 
 Hibernate pagination 
 --------------------
int pageNumber = 2;
int pageSize = 10;
Criteria criteria = session.createCriteria(Employee.class);
                criteria.setFirstResult((pageNumber - 1) * pageSize);
                criteria.setMaxResults(pageSize);
                

                
                
Unmodifiable Array List
-------------------------
public class UnmodifiableArrayList<E>  extends ArrayList<E> {

    public UnmodifiableArrayList(Collection<? extends E> c) {
        super(c);
    }

    public boolean add(int index) {
        return false;//Returning false as the element cannot be added 
    }

    public boolean addAll(Collection<? extends E> c) {
        return false;//Returning false as the element cannot be added 
    }

    public E remove(int index) {
        return null;//Returning null as the element cannot be removed
    }
}                



Singleton Java API classes
---------------------
java.lang.Runtime
java.sql.Connection & DriverManager
Toolkit
------

Concurrent HashMap - uses stripped locking technique - 16 threads can access at same time - locks only segments
Collections.SynchronizedMap() - locks whole map by synchronization - can be applied to any map using this method
Hashtable - locks whole map - legacy - slow when number of threads are more

------------------------
Hibernate states - transient, persistent, detached
More hibernate concepts
----------------------------

SMACK Stack — the common set of data services composed of 
Apache Spark (batch/stream processing), 
Apache Mesos (cluster manager), 
AKKA (JVM based actor framework), 
Apache Cassandra (storage layer), and 
Apache Kafka (message queue) — to build modern apps that utilize real-time analytics.
----------------------------


