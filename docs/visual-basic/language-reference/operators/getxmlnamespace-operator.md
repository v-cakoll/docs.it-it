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
ms.openlocfilehash: f9201aa4b2aa9280b9b3a4e0a2badf25ea819088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684749"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Operatore GetXmlNamespace (Visual Basic)
Ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Parti  
 `xmlNamespacePrefix`  
 Facoltativo. Stringa che identifica il prefisso dello spazio dei nomi XML. Se non specificato, questa stringa deve essere un identificatore XML valido. Per altre informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito. Se non viene specificato alcun spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.  
  
## <a name="return-value"></a>Valore restituito  
 Il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML.  
  
## <a name="remarks"></a>Note  
 Il `GetXmlNamespace` operatore ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.  
  
 È possibile usare i prefissi dello spazio dei nomi XML direttamente in valori letterali XML e proprietà axis XML. Tuttavia, è necessario usare il `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi per un <xref:System.Xml.Linq.XNamespace> prima di usarla nel codice dell'oggetto. È possibile aggiungere un nome dell'elemento non qualificati da un <xref:System.Xml.Linq.XNamespace> per ottenere un nome completo <xref:System.Xml.Linq.XName> dell'oggetto, quale molti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] metodi richiedono.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente importa `ns` come un prefisso dello spazio dei nomi XML. Il prefisso dello spazio dei nomi viene quindi utilizzato per creare un file XML letterale e accedere al primo nodo figlio con il nome qualificato `ns:phone`. Quindi passa tale nodo figlio per il `ShowName` subroutine, che crea un nome completo tramite il `GetXmlNamespace` operatore. Il `ShowName` subroutine passa quindi il nome completo per il <xref:System.Xml.Linq.XNode.Ancestors%2A> metodo per ottenere l'elemento padre `ns:contact` nodo.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio che contiene il testo seguente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Accesso a XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
