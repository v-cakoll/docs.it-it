---
title: Proprietà Value XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 571d9130ef69df580bbba5d90bc8758b4b627196
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349426"
---
# <a name="xml-value-property-visual-basic"></a>Proprietà Value XML (Visual Basic)

Consente di accedere al valore del primo elemento di una raccolta di oggetti <xref:System.Xml.Linq.XElement>.

## <a name="syntax"></a>Sintassi

```vb
object.Value
```

## <a name="parts"></a>Parti

|Termine|Definizione|  
|---|---|  
|`object`|Obbligatoria. Raccolta di oggetti <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Valore restituito

 `String` che contiene il valore del primo elemento della raccolta o `Nothing` se l'insieme è vuoto.

## <a name="remarks"></a>Note

 La <xref:System.Xml.Linq.XElement.Value%2A> proprietà consente di accedere facilmente al valore del primo elemento in una raccolta di oggetti <xref:System.Xml.Linq.XElement>. Questa proprietà verifica innanzitutto se la raccolta contiene almeno un oggetto. Se la raccolta è vuota, questa proprietà restituisce `Nothing`. In caso contrario, questa proprietà restituisce il valore della proprietà <xref:System.Xml.Linq.XElement.Value%2A> del primo elemento nella raccolta.

> [!NOTE]
> Quando si accede al valore di un attributo XML utilizzando l'identificatore '\@', il valore dell'attributo viene restituito come `String` e non è necessario specificare in modo esplicito la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>.

 Per accedere ad altri elementi di una raccolta, è possibile usare la proprietà dell'indicizzatore di estensione XML. Per altre informazioni, vedere [Proprietà Indexer di estensione](extension-indexer-property.md).

## <a name="inheritance"></a>Ereditarietà

 La maggior parte degli utenti non dovrà implementare <xref:System.Collections.Generic.IEnumerable%601>e pertanto può ignorare questa sezione.

 La proprietà <xref:System.Xml.Linq.XElement.Value%2A> è una proprietà di estensione per i tipi che implementano `IEnumerable(Of XElement)`. Il binding di questa proprietà di estensione è analogo all'associazione dei metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "value", la proprietà ha la precedenza sulla proprietà di estensione. In altre parole, è possibile eseguire l'override di questa proprietà <xref:System.Xml.Linq.XElement.Value%2A> definendo una nuova proprietà in una classe che implementa `IEnumerable(Of XElement)`.

## <a name="example"></a>Esempio

 Nell'esempio seguente viene illustrato come utilizzare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per accedere al primo nodo di una raccolta di oggetti <xref:System.Xml.Linq.XElement>. Nell'esempio viene utilizzata la proprietà Axis Child per ottenere la raccolta di tutti i nodi figlio denominati `phone` presenti nell'oggetto `contact`.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Questo codice visualizza il testo seguente:

 `Phone number: 206-555-0144`

## <a name="example"></a>Esempio

 Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di oggetti <xref:System.Xml.Linq.XAttribute>. Nell'esempio viene utilizzata la proprietà axis dell'attributo per visualizzare il valore dell'attributo `type` per tutti gli elementi di `phone`.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Questo codice visualizza il testo seguente:

 ```console
 home
 work
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Proprietà Axis XML](index.md)
- [Valori letterali XML](../xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Metodi di estensione](../../programming-guide/language-features/procedures/extension-methods.md)
- [Proprietà dell'indicizzatore di estensione](extension-indexer-property.md)
- [Proprietà Child Axis XML](xml-child-axis-property.md)
- [Proprietà axis dell'attributo XML](xml-attribute-axis-property.md)
