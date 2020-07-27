---
title: Gestione di coppie nome/valore (C#)
description: LINQ to XML contiene metodi che semplificano la gestione delle coppie nome/valore, sia come attributi che come set di elementi figlio.
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 92a45d160cbb1ef470d93bf740d0b6f584681e72
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165275"
---
# <a name="maintaining-namevalue-pairs-c"></a>Gestione di coppie nome/valore (C#)
In molte applicazioni è necessario gestire informazioni che è preferibile mantenere come coppie nome/valore. Queste informazioni potrebbero essere di configurazione o impostazioni globali. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] include alcuni metodi che consentono di mantenere facilmente coppie nome/valore. È possibile mantenere le informazioni come attributi o come un set di elementi figlio.  
  
 Una differenza tra il mantenere le informazioni come attributi o come elementi figlio è che gli attributi prevedono un vincolo in base al quale per un elemento può esistere un unico attributo con un nome specifico. Questa limitazione non si applica invece agli elementi figlio.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue e SetElementValue  
 I due metodi che facilitano il mantenimento delle coppie nome/valore sono <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> e <xref:System.Xml.Linq.XElement.SetElementValue%2A>. Si tratta di metodi contraddistinti da una semantica simile.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> può aggiungere, modificare o rimuovere attributi di un elemento.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo non esistente, il metodo crea un nuovo attributo e lo aggiunge all'elemento specificato.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e contenuto specificato, il contenuto dell'attributo viene sostituito con quello specificato.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e si specifica null per il contenuto, l'attributo viene rimosso dal relativo elemento padre.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> può aggiungere, modificare o rimuovere elementi figlio di un elemento.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento figlio non esistente, il metodo crea un nuovo elemento e lo aggiunge all'elemento specificato.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e contenuto specificato, il contenuto dell'elemento viene sostituito con quello specificato.  
  
- Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e si specifica null per il contenuto, l'elemento viene rimosso dal relativo elemento padre.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un elemento senza attributi. Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> per creare e gestire un elenco di coppie nome/valore.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un elemento senza elementi figlio. Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetElementValue%2A> per creare e gestire un elenco di coppie nome/valore.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [Modifica degli alberi XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
