---
title: Operatore GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 85422fb9e11d78e228577adc25cba746149c645a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371116"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Operatore GetXmlNamespace (Visual Basic)
Ottiene l' <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 Facoltativa. Stringa che identifica il prefisso dello spazio dei nomi XML. Se specificato, la stringa deve essere un identificatore XML valido. Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito. Se non viene specificato alcuno spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.  
  
## <a name="return-value"></a>Valore restituito  
 <xref:System.Xml.Linq.XNamespace>Oggetto che corrisponde al prefisso dello spazio dei nomi XML.  
  
## <a name="remarks"></a>Commenti  
 L' `GetXmlNamespace` operatore ottiene l' <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix` .  
  
 È possibile utilizzare i prefissi degli spazi dei nomi XML direttamente nei valori letterali XML e nelle proprietà Axis XML. Tuttavia, è necessario usare l' `GetXmlNamespace` operatore per convertire un prefisso dello spazio dei nomi in un <xref:System.Xml.Linq.XNamespace> oggetto prima di poterlo usare nel codice. È possibile aggiungere un nome di elemento non qualificato a un <xref:System.Xml.Linq.XNamespace> oggetto per ottenere un <xref:System.Xml.Linq.XName> oggetto completo, che richiede molti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] metodi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene importato `ns` come prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:phone` . Passa quindi quel nodo figlio alla `ShowName` subroutine, che costruisce un nome completo usando l' `GetXmlNamespace` operatore. La `ShowName` subroutine passa quindi il nome completo al <xref:System.Xml.Linq.XNode.Ancestors%2A> metodo per ottenere il `ns:contact` nodo padre.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Quando si chiama `TestGetXmlNamespace.RunSample()` , viene visualizzata una finestra di messaggio contenente il testo seguente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md)
- [Accesso a XML in Visual Basic](../../programming-guide/language-features/xml/accessing-xml.md)
