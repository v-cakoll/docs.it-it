---
title: Proprietà dell'indicizzatore di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: a7718a4aa85a000d0c83e8c9556a448ceaf13c82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603470"
---
# <a name="extension-indexer-property-visual-basic"></a>Proprietà dell'indicizzatore di estensione (Visual Basic)
Fornisce l'accesso ai singoli elementi di una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object(index)  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Obbligatorio. Una raccolta di query. Vale a dire una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.|  
|(|Obbligatorio. Indica l'inizio della proprietà dell'indicizzatore.|  
|`index`|Obbligatorio. Espressione integer che specifica la posizione in base zero di un elemento della raccolta.|  
|)|Obbligatorio. Indica la fine della proprietà dell'indicizzatore.|  
  
## <a name="return-value"></a>Valore restituito  
 L'oggetto dal percorso specificato nella raccolta, o `Nothing` se l'indice non compreso nell'intervallo.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi in una raccolta. Questa proprietà dell'indicizzatore è in genere utilizzata nell'output di una proprietà axis XML. L'elemento figlio XML e proprietà axis descendant XML restituiscono raccolte di <xref:System.Xml.Linq.XElement> oggetti o un valore di attributo.  
  
 Il compilatore Visual Basic converte le proprietà dell'indicizzatore di estensione per le chiamate al `ElementAtOrDefault` metodo. A differenza di un indicizzatore di matrice, il `ElementAtOrDefault` restituisce `Nothing` se l'indice non compreso nell'intervallo. Questo comportamento è utile quando non è possibile determinare facilmente il numero di elementi in una raccolta.  
  
 Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: viene utilizzato solo se la raccolta non ha un indicizzatore o una proprietà predefinita.  
  
 Per accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> oggetti, è possibile utilizzare il codice XML `Value` proprietà. Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. La raccolta è accessibile tramite la proprietà asse figlio, che ottiene tutti gli elementi figlio denominati `phone` nel `contact` oggetto.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
