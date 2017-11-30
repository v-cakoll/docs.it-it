---
title: Operatore GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Operatore GetXmlNamespace (Visual Basic)
Ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 Parametro facoltativo. Stringa che identifica il prefisso dello spazio dei nomi XML. Se fornito, questa stringa deve essere un identificatore XML valido. Per ulteriori informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito. Se non viene specificato alcun spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.  
  
## <a name="return-value"></a>Valore restituito  
 Il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML.  
  
## <a name="remarks"></a>Note  
 Il `GetXmlNamespace` operatore ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.  
  
 È possibile utilizzare i prefissi di spazio dei nomi XML direttamente in valori letterali XML e proprietà axis XML. Tuttavia, è necessario utilizzare il `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi per un <xref:System.Xml.Linq.XNamespace> dell'oggetto prima che sia possibile utilizzarlo nel codice. È possibile aggiungere un nome dell'elemento non qualificati da un <xref:System.Xml.Linq.XNamespace> oggetto da ottenere un nome completo <xref:System.Xml.Linq.XName> dell'oggetto, quale molti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] metodi richiedono.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa `ns` come un prefisso dello spazio dei nomi XML. Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al primo nodo figlio con il nome completo `ns:phone`. Passa quindi tale nodo figlio per il `ShowName` subroutine, che costruisce un nome completo utilizzando il `GetXmlNamespace` operatore. Il `ShowName` subroutine passa quindi il nome completo per il <xref:System.Xml.Linq.XNode.Ancestors%2A> metodo per ottenere l'elemento padre `ns:contact` nodo.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio che contiene il testo seguente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Accesso a XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
