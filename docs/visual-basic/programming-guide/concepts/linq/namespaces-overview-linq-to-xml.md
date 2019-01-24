---
title: Panoramica degli spazi dei nomi (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
ms.openlocfilehash: b2ea4c28fe14e57d3f72bb29d4960f436bbd9bb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603701"
---
# <a name="namespaces-overview-linq-to-xml"></a>Panoramica degli spazi dei nomi (LINQ to XML)
In questo argomento vengono presentati gli spazi dei nomi, la classe <xref:System.Xml.Linq.XName> e la classe <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Nomi XML  
 I nomi XML sono spesso causa di complessità nella programmazione XML. Un nome XML è composto da uno spazio dei nomi XML (detto anche URI dello spazio dei nomi XML) e da un nome locale. Uno spazio dei nomi XML è simile a uno spazio di nomi in un'applicazione basata su [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Consente infatti di qualificare in modo univoco i nomi di elementi e attributi e quindi di evitare conflitti di nomi tra le diverse parti di un documento XML. Dopo aver dichiarato uno spazio dei nomi XML, è possibile selezionare un nome locale che deve essere univoco all'interno di tale spazio dei nomi.  
  
 Un'altra peculiarità dei nomi XML è costituita dai *prefissi di spazio dei nomi* XML. Sono i prefissi XML a costituire la causa di maggior complessità dei nomi XML. I prefissi consentono di creare un collegamento per uno spazio dei nomi XML al fine di rendere il documento XML più conciso e comprensibile. Tuttavia, il significato dei prefissi XML dipende dal contesto ed è proprio questo aspetto a renderli complessi. Ad esempio, è possibile associare il prefisso XML `aw` a un unico spazio dei nomi XML in un'unica parte di un albero XML e a uno spazio dei nomi XML diverso in una parte diversa dell'albero XML.  
  
 Quando si usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con i valori letterali XML e Visual Basic, è necessario usare prefissi dello spazio dei nomi quando si lavora con i documenti in spazi dei nomi.  
  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] la classe che rappresenta i nomi XML è <xref:System.Xml.Linq.XName>. I nomi XML vengono usati frequentemente in tutta l'API di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Nei casi in cui è richiesto un nome XML, sarà presente un parametro <xref:System.Xml.Linq.XName>. Solo in casi rari, tuttavia, si usa direttamente un oggetto <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> contiene una conversione implicita da stringa.  
  
 Per altre informazioni, vedere <xref:System.Xml.Linq.XNamespace> e <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Vedere anche
- [Utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
