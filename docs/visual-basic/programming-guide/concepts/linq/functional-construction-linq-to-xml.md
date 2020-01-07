---
title: Costruzione funzionale (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
ms.openlocfilehash: a51360d6c8d44770c462afb728a1fb78d3e2cd42
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636848"
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Costruzione funzionale (LINQ to XML) (Visual Basic)
In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è disponibile una potente funzionalità per la creazione di elementi XML, denominata *costruzione funzionale*. Per costruzione funzionale si intende la possibilità di creare una struttura ad albero XML in un'unica istruzione.  
  
 Diverse funzionalità importanti dell'interfaccia di programmazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono la costruzione funzionale:  
  
- Il costruttore <xref:System.Xml.Linq.XElement> accetta vari tipi di argomenti come contenuto. Ad esempio, è possibile passare un altro oggetto <xref:System.Xml.Linq.XElement>, che diventa un elemento figlio. È possibile passare un oggetto <xref:System.Xml.Linq.XAttribute>, che diventa un attributo dell'elemento. Oppure è possibile passare qualsiasi altro tipo di oggetto, che viene convertito in una stringa e diventa il contenuto di testo dell'elemento.  
  
- Il costruttore <xref:System.Xml.Linq.XElement> accetta una matrice `params` di tipo <xref:System.Object>, quindi è possibile passare qualsiasi numero di oggetti. In questo modo è possibile creare un elemento con contenuto complesso.  
  
- Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi della raccolta. Se la raccolta contiene oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, ogni elemento della raccolta viene aggiunto separatamente. Questo è importante perché consente di passare i risultati di una query LINQ al costruttore.  
  
 Di seguito si riporta un esempio.  
  
 Queste funzionalità consentono di scrivere codice usando valori letterali XML per creare un albero XML e anche di scrivere codice che usa i risultati delle query LINQ quando si crea un albero XML:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
