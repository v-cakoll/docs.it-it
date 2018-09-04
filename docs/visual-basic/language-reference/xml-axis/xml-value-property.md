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
ms.openlocfilehash: 2b0719320db5843d5d010bfbd70e551646e3ded9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533391"
---
# <a name="xml-value-property-visual-basic"></a>Proprietà Value XML (Visual Basic)
Fornisce l'accesso al valore del primo elemento di una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Obbligatorio. Raccolta di oggetti <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto `String` che contiene il valore del primo elemento della raccolta, o `Nothing` se la raccolta è vuota.  
  
## <a name="remarks"></a>Note  
 Il <xref:System.Xml.Linq.XElement.Value%2A> proprietà rende più semplice accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. Questa proprietà controlla innanzitutto se la raccolta contiene almeno un oggetto. Se la raccolta è vuota, questa proprietà restituisce `Nothing`. In caso contrario, questa proprietà restituisce il valore della <xref:System.Xml.Linq.XElement.Value%2A> proprietà del primo elemento nella raccolta.  
  
> [!NOTE]
>  Quando si accede al valore di un attributo XML utilizzando il '\@' identificatore, viene restituito il valore dell'attributo come un `String` e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.  
  
 Per accedere agli altri elementi in una raccolta, è possibile usare la proprietà dell'indicizzatore di estensione XML. Per altre informazioni, vedere [proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Ereditarietà  
 La maggior parte degli utenti non dovranno implementare <xref:System.Collections.Generic.IEnumerable%601>e pertanto possono ignorare questa sezione.  
  
 Il <xref:System.Xml.Linq.XElement.Value%2A> è una proprietà estensione per i tipi che implementano `IEnumerable(Of XElement)`. L'associazione di questa proprietà di estensione è simile all'associazione di metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "Value", tale proprietà ha la precedenza sulla proprietà di estensione. In altre parole, ciò <xref:System.Xml.Linq.XElement.Value%2A> può eseguire l'override di proprietà mediante la definizione di una nuova proprietà in una classe che implementa `IEnumerable(Of XElement)`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Xml.Linq.XElement.Value%2A> per accedere al primo nodo in una raccolta di proprietà <xref:System.Xml.Linq.XElement> oggetti. L'esempio Usa la proprietà child axis per ottenere la raccolta di tutti i nodi figlio denominati `phone` che si trovano i `contact` oggetto.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di <xref:System.Xml.Linq.XAttribute> oggetti. L'esempio Usa la proprietà axis dell'attributo per visualizzare il valore della `type` attributo per tutti i `phone` elementi.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [Proprietà Child Axis XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Proprietà axis dell'attributo XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
