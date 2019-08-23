---
title: Proprietà Value XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942985"
---
# <a name="xml-value-property-visual-basic"></a>Proprietà Value XML (Visual Basic)
Consente di accedere al valore del primo elemento di una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Richiesto. Raccolta di oggetti <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto `String` che contiene il valore del primo elemento della raccolta o `Nothing` se l'insieme è vuoto.  
  
## <a name="remarks"></a>Note  
 La <xref:System.Xml.Linq.XElement.Value%2A> proprietà consente di accedere facilmente al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. Questa proprietà verifica innanzitutto se la raccolta contiene almeno un oggetto. Se la raccolta è vuota, questa proprietà restituisce `Nothing`. In caso contrario, questa proprietà restituisce il valore <xref:System.Xml.Linq.XElement.Value%2A> della proprietà del primo elemento nella raccolta.  
  
> [!NOTE]
> Quando si accede al valore di un attributo XML usando l'identificatore\@'', il valore dell'attributo viene restituito `String` come e non è necessario specificare in modo esplicito la <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.  
  
 Per accedere ad altri elementi di una raccolta, è possibile usare la proprietà dell'indicizzatore di estensione XML. Per altre informazioni, vedere [Proprietà Indexer di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Ereditarietà  
 La maggior parte degli utenti non dovrà <xref:System.Collections.Generic.IEnumerable%601>implementare e pertanto può ignorare questa sezione.  
  
 La <xref:System.Xml.Linq.XElement.Value%2A> proprietà è una proprietà di estensione per i tipi `IEnumerable(Of XElement)`che implementano. Il binding di questa proprietà di estensione è analogo all'associazione dei metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "value", la proprietà ha la precedenza sulla proprietà di estensione. In altre parole, è <xref:System.Xml.Linq.XElement.Value%2A> possibile eseguire l'override di questa proprietà definendo una nuova proprietà in una classe che `IEnumerable(Of XElement)`implementa.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Xml.Linq.XElement.Value%2A> proprietà per accedere al primo nodo di una raccolta di <xref:System.Xml.Linq.XElement> oggetti. Nell'esempio viene utilizzata la proprietà Axis Child per ottenere la raccolta di tutti i nodi `phone` figlio denominati `contact` presenti nell'oggetto.  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di <xref:System.Xml.Linq.XAttribute> oggetti. Nell'esempio viene utilizzata la proprietà axis dell'attributo per visualizzare il valore `type` dell'attributo per tutti `phone` gli elementi.  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 Questo codice visualizza il testo seguente:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [Proprietà Child Axis XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Proprietà axis dell'attributo XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
