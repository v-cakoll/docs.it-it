---
title: Proprietà axis dell'attributo XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9968e5de0f8cb45fb896ba43c80d9c9a3ab8ef08
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
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
 Obbligatorio. Un <xref:System.Xml.Linq.XElement> oggetto o una raccolta di <xref:System.Xml.Linq.XElement> oggetti.  
  
 .@  
 Obbligatorio. Indica l'inizio di una proprietà axis dell'attributo.  
  
 <  
 Facoltativo. Indica l'inizio del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.  
  
 `attribute`  
 Obbligatorio. Nome dell'attributo a cui accedere, nel formato [`prefix`:]`name`.  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`prefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.|  
|`name`|Obbligatorio. Nome locale dell'attributo. Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Facoltativo. Indica la fine del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.  
  
## <a name="return-value"></a>Valore restituito  
 Stringa che contiene il valore di `attribute`. Se il nome dell'attributo non esiste, `Nothing` viene restituito.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare una proprietà axis dell'attributo XML per accedere al valore di un attributo con nome di un <xref:System.Xml.Linq.XElement> oggetti o tra il primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti. È possibile recuperare un valore di attributo in base al nome o aggiungere un nuovo attributo a un elemento specificando un nuovo nome preceduto dall'identificatore @.  
  
 Quando si fa riferimento a un attributo XML utilizzando l'identificatore @, viene restituito il valore dell'attributo sotto forma di stringa e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.  
  
 Le regole di denominazione per gli attributi XML sono diversi dalle regole di denominazione per gli identificatori di Visual Basic. Per accedere a un attributo XML con un nome che non è un valido identificatore Visual Basic, racchiudere il nome tra parentesi acute (\< e >).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Il nome di una proprietà axis dell'attributo può utilizzare solo i prefissi dello spazio dei nomi XML dichiarati globalmente con il `Imports` istruzione. Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML. Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere i valori degli attributi XML denominati `type` da una raccolta di elementi XML denominati `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare attributi per un elemento XML sia in modo dichiarativo, come parte del codice XML e, in modo dinamico aggiungendo un attributo a un'istanza di un <xref:System.Xml.Linq.XElement> oggetto. Il `type` l'attributo viene creato in modo dichiarativo e `owner` attributo viene creato dinamicamente.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la sintassi di parentesi uncinate per ottenere il valore dell'attributo XML denominato `number-type`, che non è un identificatore valido in Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: work`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al primo nodo figlio con il nome completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
