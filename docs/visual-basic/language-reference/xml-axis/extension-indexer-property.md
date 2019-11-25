---
title: Proprietà dell'indicizzatore di estensione
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352691"
---
# <a name="extension-indexer-property-visual-basic"></a>Proprietà dell'indicizzatore di estensione (Visual Basic)
Fornisce l'accesso ai singoli elementi di una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Obbligatorio. A queryable collection. That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.|  
|(|Obbligatorio. Denotes the start of the indexer property.|  
|`index`|Obbligatorio. An integer expression that specifies the zero-based position of an element of the collection.|  
|)|Obbligatorio. Denotes the end of the indexer property.|  
  
## <a name="return-value"></a>Valore restituito  
 The object from the specified location in the collection, or `Nothing` if the index is out of range.  
  
## <a name="remarks"></a>Note  
 You can use the extension indexer property to access individual elements in a collection. This indexer property is typically used on the output of XML axis properties. The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.  
  
 The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method. Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range. This behavior is useful when you cannot easily determine the number of elements in a collection.  
  
 This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.  
  
 To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property. For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Esempio  
 The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects. The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
