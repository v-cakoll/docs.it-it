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
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401342"
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
|`object`|Obbligatorio. Raccolta Queryable. Ovvero una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .|  
|(|Obbligatorio. Indica l'inizio della proprietà dell'indicizzatore.|  
|`index`|Obbligatorio. Espressione Integer che specifica la posizione in base zero di un elemento della raccolta.|  
|)|Obbligatorio. Indica la fine della proprietà dell'indicizzatore.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto dalla posizione specificata nella raccolta o `Nothing` se l'indice non è compreso nell'intervallo.  
  
## <a name="remarks"></a>Commenti  
 È possibile usare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi di una raccolta. Questa proprietà dell'indicizzatore viene in genere utilizzata nell'output delle proprietà Axis XML. Le proprietà dell'asse XML figlio e XML discendente restituiscono raccolte di <xref:System.Xml.Linq.XElement> oggetti o un valore di attributo.  
  
 Il compilatore Visual Basic converte le proprietà dell'indicizzatore di estensione in chiamate al `ElementAtOrDefault` metodo. Diversamente da un indicizzatore di matrici, il `ElementAtOrDefault` metodo restituisce `Nothing` se l'indice non è compreso nell'intervallo. Questo comportamento è utile quando non è possibile determinare facilmente il numero di elementi in una raccolta.  
  
 Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> : viene utilizzata solo se la raccolta non dispone di un indicizzatore o di una proprietà predefinita.  
  
 Per accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti o <xref:System.Xml.Linq.XAttribute> , è possibile usare la proprietà XML `Value` . Per ulteriori informazioni, vedere [proprietà del valore XML](xml-value-property.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. È possibile accedere alla raccolta utilizzando la proprietà Axis figlio, che ottiene tutti gli elementi figlio denominati `phone` nell' `contact` oggetto.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](index.md)
- [Valori letterali XML](../xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Proprietà Value XML](xml-value-property.md)
