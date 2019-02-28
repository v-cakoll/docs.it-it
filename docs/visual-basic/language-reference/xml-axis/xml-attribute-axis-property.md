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
ms.openlocfilehash: 081359f32438c6474fe5c229634b60969e25a24e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965384"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Proprietà axis dell'attributo XML (Visual Basic)
Fornisce l'accesso al valore di un attributo per un <xref:System.Xml.Linq.XElement> oggetto o al primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Parti  
 `object`  
 Obbligatorio. Un' <xref:System.Xml.Linq.XElement> oggetto o una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
 .@  
 Obbligatorio. Indica l'inizio di una proprietà axis dell'attributo.  
  
 <  
 Facoltativo. Indica l'inizio del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.  
  
 `attribute`  
 Obbligatorio. Nome dell'attributo a cui accedere, nel formato [`prefix`:]`name`.  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`prefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.|  
|`name`|Obbligatorio. Nome locale dell'attributo. Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Facoltativo. Indica la fine del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.  
  
## <a name="return-value"></a>Valore restituito  
 Stringa che contiene il valore di `attribute`. Se il nome dell'attributo non esiste, `Nothing` viene restituito.  
  
## <a name="remarks"></a>Note  
 È possibile usare una proprietà asse attributo XML per accedere al valore di un attributo in base al nome da un <xref:System.Xml.Linq.XElement> oggetto o tra il primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. È possibile recuperare un valore di attributo in base al nome o aggiungere un nuovo attributo a un elemento specificando un nuovo nome preceduto dal @ identificatore.  
  
 Quando fa riferimento a un attributo XML con l'identificatore @, viene restituito il valore dell'attributo sotto forma di stringa e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.  
  
 Le regole di denominazione per gli attributi XML differiscono dalle regole di denominazione per gli identificatori di Visual Basic. Per accedere a un attributo XML che ha un nome che non è un valido identificatore Visual Basic, racchiuderlo tra parentesi angolari (\< e >).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Il nome di una proprietà axis dell'attributo può usare solo i prefissi dello spazio dei nomi XML dichiarati a livello globale usando il `Imports` istruzione. Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML. Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere i valori degli attributi XML denominati `type` da una raccolta di elementi XML che sono denominate `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Questo codice visualizza il testo seguente:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare in modo dichiarativo, come parte del codice XML e in modo dinamico mediante l'aggiunta di un attributo a un'istanza di attributi per un elemento XML sia un <xref:System.Xml.Linq.XElement> oggetto. Il `type` l'attributo viene creato in modo dichiarativo e `owner` attributo viene creato dinamicamente.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la sintassi di parentesi uncinate per ottenere il valore dell'attributo XML denominato `number-type`, che non è un identificatore valido in Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: work`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Il prefisso dello spazio dei nomi viene quindi utilizzato per creare un file XML letterale e accedere al primo nodo figlio con il nome completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
