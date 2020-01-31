---
title: Utilizzo di System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 2ecb709684834a8280c841eb8eef4f024481f7a4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743577"
---
# <a name="systemxml-usage"></a>Utilizzo di System.Xml
In questa sezione viene descritto l'utilizzo di diversi tipi che risiedono in <xref:System.Xml?displayProperty=nameWithType> spazi dei nomi che possono essere utilizzati per rappresentare i dati XML.

 ❌ non utilizzare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML. Preferire l'utilizzo di istanze di <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>o sottotipi di <xref:System.Xml.Linq.XNode>. `XmlNode` e `XmlDocument` non sono progettate per l'esposizione in API pubbliche.

 ✔️ utilizzare `XmlReader`, `IXPathNavigable`o sottotipi di `XNode` come input o output di membri che accettano o restituiscono XML.

 Usare queste astrazioni invece di `XmlDocument`, `XmlNode`o <xref:System.Xml.XPath.XPathDocument>, perché questo separa i metodi da implementazioni specifiche di un documento XML in memoria e consente loro di lavorare con origini dati XML virtuali che espongono `XNode`, `XmlReader`o <xref:System.Xml.XPath.XPathNavigator>.

 NON ❌ sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una vista XML di un modello a oggetti sottostante o di un'origine dati.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
