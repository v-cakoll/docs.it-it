---
title: Utilizzo di System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce9869d538b69af9beaa74be3300175f279b8f53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572814"
---
# <a name="systemxml-usage"></a>Utilizzo di System.Xml
In questa sezione discute relativo all'utilizzo di diversi tipi che si trovano <xref:System.Xml?displayProperty=nameWithType> gli spazi dei nomi che può essere usato per rappresentare i dati XML.  
  
 **X DO NOT** usare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML. Preferire l'utilizzo di istanze di <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o sottotipi di <xref:System.Xml.Linq.XNode> invece. `XmlNode` e `XmlDocument` non sono progettati per l'esposizione di API pubbliche.  
  
 **✓ DO** usare `XmlReader`, `IXPathNavigable`, o sottotipi di `XNode` come input o output di membri che accettano o restituiscono XML.  
  
 Utilizzare queste astrazioni anziché `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, perché questo separa i metodi delle implementazioni specifiche di un documento XML in memoria e consente loro di lavorare con le origini dati XML virtuale che espongono `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una vista XML di un'origine dati o modello di oggetto sottostante.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
