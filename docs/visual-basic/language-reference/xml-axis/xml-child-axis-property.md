---
title: "Proprietà Child Axis XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea4db763bbed651a01845b49395255586cb60113
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-child-axis-property-visual-basic"></a>Proprietà Child Axis XML (Visual Basic)
Fornisce l'accesso agli elementi figlio di uno dei seguenti oggetti: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument>, raccolta di <xref:System.Xml.Linq.XElement> o raccolta di <xref:System.Xml.Linq.XDocument>.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object.<child>  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`object`|Obbligatorio. Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.|  
|.<|Obbligatorio. Indica l'inizio di una proprietà axis dell'elemento figlio.|  
|`child`|Obbligatorio. Nome dei nodi figlio a cui accedere, nel formato [`prefix``:`]`name`.<br /><br /> -   `Prefix`-Facoltativo. Prefisso dello spazio dei nomi XML per il nodo figlio. Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.<br />-   `Name`-Obbligatorio. Nome del nodo figlio locale. Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Obbligatorio. Indica la fine di una proprietà axis dell'elemento figlio.|  
  
## <a name="return-value"></a>Valore restituito  
 Raccolta di oggetti <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Note  
 È possibile usare una proprietà axis dell'elemento figlio XML per accedere a nodi figlio in base al nome, da un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> o da raccolte di oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>. Usare la proprietà `Value` XML per accedere al valore del primo nodo figlio nella raccolta restituita. Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte le proprietà asse figlio in chiamate al <xref:System.Xml.Linq.XContainer.Elements%2A> metodo.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Il nome in una proprietà axis dell'elemento figlio può usare solo prefissi degli spazi dei nomi XML dichiarati globalmente con l'istruzione `Imports`. Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML. Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dall'oggetto `contact`.  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dalla raccolta restituita dalla proprietà axis dell'elemento figlio `contact` dell'oggetto `contacts`.  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
