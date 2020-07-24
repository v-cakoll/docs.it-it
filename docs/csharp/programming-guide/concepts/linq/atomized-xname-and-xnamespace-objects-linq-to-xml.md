---
title: Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)
description: Informazioni sugli oggetti XName e XNamespace atomizzati e sul modo in cui forniscono i vantaggi delle prestazioni per le query.
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: 305a233adab5c860b5f9509ae25ccc5d633e7957
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104285"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a>Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)
Gli oggetti <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> sono *atomizzati*, ovvero, se contengono lo stesso nome completo fanno riferimento allo stesso oggetto. Questo offre vantaggi a livello di prestazioni per le query: quando si confrontano due nomi atomizzati per verificarne l'uguaglianza, il linguaggio intermedio sottostante deve determinare solo se i due riferimenti puntano allo stesso oggetto. Il codice sottostante non deve eseguire confronti tra stringhe, che richiederebbero molto tempo.  
  
## <a name="atomization-semantics"></a>Semantica di atomizzazione  
 Atomizzazione significa che se due oggetti <xref:System.Xml.Linq.XName> hanno lo stesso nome locale e si trovano nello stesso spazio dei nomi, condividono la stessa istanza. Analogamente, se due oggetti <xref:System.Xml.Linq.XNamespace> hanno lo stesso URI dello spazio dei nomi, condividono la stessa istanza.  
  
 Affinché una classe consenta gli oggetti atomizzati, il costruttore per la classe deve essere privato, non pubblico. Se il costruttore fosse pubblico, sarebbe possibile creare un oggetto non atomizzato. Le classi <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> implementano un operatore di conversione implicita per la conversione di una stringa in un oggetto <xref:System.Xml.Linq.XName> o <xref:System.Xml.Linq.XNamespace>. In questo modo è possibile ottenere un'istanza di questi oggetti. Non è possibile ottenere un'istanza tramite un costruttore, in quanto il costruttore è inaccessibile.  
  
 <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> implementano anche gli operatori di uguaglianza e di disuguaglianza, per determinare se i due oggetti confrontati sono riferimenti alla stessa istanza.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente vengono creati alcuni oggetti <xref:System.Xml.Linq.XElement> e viene dimostrato che i nomi identici condividono la stessa istanza.  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Come illustrato in precedenza, il vantaggio degli oggetti atomizzati consiste nel fatto che quando si usa uno dei metodi dell'asse che accettano <xref:System.Xml.Linq.XName> come parametro, il metodo dell'asse deve determinare solo che due nomi fanno riferimento alla stessa istanza per selezionare gli elementi desiderati.  
  
 Nell'esempio seguente viene passato un oggetto <xref:System.Xml.Linq.XName> alla chiamata al metodo <xref:System.Xml.Linq.XContainer.Descendants%2A>, le cui prestazioni sono quindi migliori grazie al modello di atomizzazione.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
