---
title: Operatore GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592160"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Operatore GetXmlNamespace (Visual Basic)
Ottiene l'oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 facoltativo. Stringa che identifica il prefisso dello spazio dei nomi XML. Se specificato, la stringa deve essere un identificatore XML valido. Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito. Se non viene specificato alcuno spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML.  
  
## <a name="remarks"></a>Note  
 L'operatore `GetXmlNamespace` Ottiene l'oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.  
  
 È possibile utilizzare i prefissi degli spazi dei nomi XML direttamente nei valori letterali XML e nelle proprietà Axis XML. Tuttavia, è necessario usare l'operatore `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi in un oggetto <xref:System.Xml.Linq.XNamespace> prima di poterlo usare nel codice. È possibile aggiungere un nome di elemento non qualificato a un oggetto <xref:System.Xml.Linq.XNamespace> per ottenere un oggetto <xref:System.Xml.Linq.XName> completo, che richiede molti metodi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene importato `ns` come prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:phone`. Passa quindi quel nodo figlio alla subroutine `ShowName`, che costruisce un nome completo usando l'operatore `GetXmlNamespace`. La subroutine `ShowName` passa quindi il nome completo al metodo <xref:System.Xml.Linq.XNode.Ancestors%2A> per ottenere il nodo padre `ns:contact`.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio contenente il testo seguente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Accesso a XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
