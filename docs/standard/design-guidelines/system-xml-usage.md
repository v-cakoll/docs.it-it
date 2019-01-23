---
title: Utilizzo di System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fc94ac62d1f2413c5f51446a8f6d0a52d9151557
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497956"
---
# <a name="systemxml-usage"></a>Utilizzo di System.Xml
Questa sezione illustra l'utilizzo dei vari tipi che si trovano <xref:System.Xml?displayProperty=nameWithType> gli spazi dei nomi che può essere utilizzato per rappresentare i dati XML.  
  
 **X DO NOT** usare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML. Preferire l'utilizzo di istanze di <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o sottotipi di <xref:System.Xml.Linq.XNode> invece. `XmlNode` e `XmlDocument` non sono progettati per l'esposizione delle API pubbliche.  
  
 **✓ DO** usare `XmlReader`, `IXPathNavigable`, o sottotipi di `XNode` come input o output di membri che accettano o restituiscono XML.  
  
 Usare queste astrazioni anziché `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, in quanto ciò consente di disaccoppiare i metodi da implementazioni specifiche di un documento XML in memoria e consente loro di lavorare con le origini dati XML virtuale che espongono `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una vista XML di un'origine dati o modello di oggetto sottostante.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
