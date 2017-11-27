---
title: Gestione di coppie nome-valore (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2743b7ce09db2ec2695c04eeef631a33fa2c289
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="maintaining-namevalue-pairs-visual-basic"></a>Gestione di coppie nome/valore (Visual Basic)
In molte applicazioni è necessario gestire informazioni che è preferibile mantenere come coppie nome/valore. Queste informazioni potrebbero essere di configurazione o impostazioni globali. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] include alcuni metodi che consentono di mantenere facilmente coppie nome/valore. È possibile mantenere le informazioni come attributi o come un set di elementi figlio.  
  
 Una differenza tra il mantenere le informazioni come attributi o come elementi figlio è che gli attributi prevedono un vincolo in base al quale per un elemento può esistere un unico attributo con un nome specifico. Questa limitazione non si applica invece agli elementi figlio.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue e SetElementValue  
 I due metodi che facilitano il mantenimento delle coppie nome/valore sono <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> e <xref:System.Xml.Linq.XElement.SetElementValue%2A>. Si tratta di metodi contraddistinti da una semantica simile.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> può aggiungere, modificare o rimuovere attributi di un elemento.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo non esistente, il metodo crea un nuovo attributo e lo aggiunge all'elemento specificato.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e contenuto specificato, il contenuto dell'attributo viene sostituito con quello specificato.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con un nome di un attributo esistente e si specifica null per il contenuto, l'attributo viene rimosso dal relativo elemento padre.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> può aggiungere, modificare o rimuovere elementi figlio di un elemento.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento figlio non esistente, il metodo crea un nuovo elemento e lo aggiunge all'elemento specificato.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e contenuto specificato, il contenuto dell'elemento viene sostituito con quello specificato.  
  
-   Se si chiama <xref:System.Xml.Linq.XElement.SetElementValue%2A> con un nome di un elemento esistente e si specifica null per il contenuto, l'elemento viene rimosso dal relativo elemento padre.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un elemento senza attributi. Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> per creare e gestire un elenco di coppie nome/valore.  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un elemento senza elementi figlio. Viene quindi usato il metodo <xref:System.Xml.Linq.XElement.SetElementValue%2A> per creare e gestire un elenco di coppie nome/valore.  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 Questo esempio produce il seguente output:  
  
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
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>  
 [Modifica degli alberi XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
