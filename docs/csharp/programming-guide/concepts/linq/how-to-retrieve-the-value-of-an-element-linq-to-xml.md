---
title: Come recuperare il valore di un elemento (LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: c4bb78e937fe0de08242923cdd7cd638abf571c7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805827"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Come recuperare il valore di un elemento (LINQ to XML) (C

In questo articolo viene illustrato come ottenere il valore degli elementi. Ci sono due modi principali per ottenere il valore:

- Eseguire <xref:System.Xml.Linq.XElement> il <xref:System.Xml.Linq.XAttribute> cast di un o an al tipo desiderato. L'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo nel tipo specificato e lo assegna alla variabile.

- Utilizzare <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> le <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> proprietà o . È inoltre possibile impostare il valore utilizzando queste proprietà.

Con C , il cast è in genere l'approccio migliore. Se si esegue il cast dell'elemento o dell'attributo su un tipo di valore nullable, il codice è più semplice da scrivere quando si recupera il valore di un elemento (o attributo) che potrebbe o meno esistere. [L'ultimo esempio](#element-might-not-exist-example) in questo articolo dimostra che il cast è più semplice nel caso in cui l'elemento potrebbe non esistere. Tuttavia, non è possibile impostare il contenuto di un elemento tramite cast, operazione che è invece eseguibile tramite la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.  
  
## <a name="string-cast-example"></a>Esempio di cast di stringhe  
 Per recuperare il valore di <xref:System.Xml.Linq.XElement> un elemento, eseguire il cast dell'oggetto al tipo desiderato. È possibile eseguire il cast di un elemento in una stringa, come indicato di seguito:You can cast an element to a string, as follows:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a>Esempio di cast di IntegerInteger  
 È anche possibile eseguire il cast di elementi in tipi diversi da stringa. Ad esempio, se un elemento contiene un Integer, è possibile eseguirne il cast in `int`, come illustrato nel codice seguente:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce operatori di cast espliciti per i seguenti tipi di dati: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce gli stessi operatori di cast per gli oggetti <xref:System.Xml.Linq.XAttribute>.  
  
## <a name="value-property-example"></a>Esempio di proprietà Value  
 È possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per recuperare il contenuto di un elemento:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a>L'elemento potrebbe non esistere nell'esempio
 A volte si tenta di recuperare il valore di un elemento anche se non si è sicuri se esiste. In questo caso, quando si assegna l'elemento di cui è stato eseguito il cast a un `null`tipo di riferimento nullable o a un tipo di valore nullable, se l'elemento non esiste, la variabile assegnata viene impostata su . Nel codice seguente viene dimostrato che quando non si è certi che l'elemento esista, è preferibile eseguire il cast anziché usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A>.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 L'output del codice è il seguente:  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 In generale, è possibile scrivere codice più semplice quando si usa il cast per recuperare il contenuto di elementi e attributi.  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
