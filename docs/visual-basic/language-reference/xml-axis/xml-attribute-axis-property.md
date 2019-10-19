---
title: Proprietà axis dell'attributo XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 896081c3dc7ca9e50b4dc4bd87675e957c34b649
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582157"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Proprietà axis dell'attributo XML (Visual Basic)
Consente di accedere al valore di un attributo per un oggetto <xref:System.Xml.Linq.XElement> o al primo elemento di una raccolta di oggetti <xref:System.Xml.Linq.XElement>.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Parti  
 `object`  
 Obbligatorio. Oggetto <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XElement>.  
  
 .@  
 Obbligatorio. Indica l'inizio di una proprietà axis dell'attributo.  
  
 <  
 Parametro facoltativo. Indica l'inizio del nome dell'attributo quando `attribute` non è un identificatore valido nel Visual Basic.  
  
 `attribute`  
 Obbligatorio. Nome dell'attributo a cui accedere, nel formato [`prefix`:] `name`.  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`prefix`|Parametro facoltativo. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.|  
|`name`|Obbligatorio. Nome dell'attributo locale. Vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Parametro facoltativo. Indica la fine del nome dell'attributo quando `attribute` non è un identificatore valido nel Visual Basic.  
  
## <a name="return-value"></a>Valore restituito  
 Stringa che contiene il valore di `attribute`. Se il nome dell'attributo non esiste, viene restituito `Nothing`.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare una proprietà axis dell'attributo XML per accedere al valore di un attributo in base al nome da un oggetto <xref:System.Xml.Linq.XElement> o dal primo elemento di una raccolta di oggetti <xref:System.Xml.Linq.XElement>. È possibile recuperare un valore di attributo in base al nome o aggiungere un nuovo attributo a un elemento specificando un nuovo nome preceduto da @ Identifier.  
  
 Quando si fa riferimento a un attributo XML usando l'identificatore @, il valore dell'attributo viene restituito come stringa e non è necessario specificare in modo esplicito la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Le regole di denominazione per gli attributi XML sono diverse dalle regole di denominazione per gli identificatori di Visual Basic. Per accedere a un attributo XML con un nome diverso da un identificatore di Visual Basic valido, racchiudere il nome tra parentesi acute (\< e >).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Il nome in una proprietà axis dell'attributo può utilizzare solo i prefissi degli spazi dei nomi XML dichiarati globalmente utilizzando l'istruzione `Imports`. Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML. Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere i valori degli attributi XML denominati `type` da una raccolta di elementi XML denominati `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Questo codice visualizza il testo seguente:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare attributi per un elemento XML in modo dichiarativo, come parte del codice XML, e in modo dinamico aggiungendo un attributo a un'istanza di un oggetto <xref:System.Xml.Linq.XElement>. L'attributo `type` viene creato in modo dichiarativo e l'attributo `owner` viene creato dinamicamente.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la sintassi della parentesi uncinata per ottenere il valore dell'attributo XML denominato `number-type`, che non è un identificatore valido nella Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: work`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
