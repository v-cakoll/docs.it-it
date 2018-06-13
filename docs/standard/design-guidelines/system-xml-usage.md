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
# <a name="systemxml-usage"></a><span data-ttu-id="dc577-102">Utilizzo di System.Xml</span><span class="sxs-lookup"><span data-stu-id="dc577-102">System.Xml Usage</span></span>
<span data-ttu-id="dc577-103">In questa sezione discute relativo all'utilizzo di diversi tipi che si trovano <xref:System.Xml?displayProperty=nameWithType> gli spazi dei nomi che può essere usato per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="dc577-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="dc577-104">**X non** usare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="dc577-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="dc577-105">Preferire l'utilizzo di istanze di <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o sottotipi di <xref:System.Xml.Linq.XNode> invece.</span><span class="sxs-lookup"><span data-stu-id="dc577-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="dc577-106">`XmlNode` e `XmlDocument` non sono progettati per l'esposizione di API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="dc577-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="dc577-107">**✓ SI** usare `XmlReader`, `IXPathNavigable`, o sottotipi di `XNode` come input o output di membri che accettano o restituiscono XML.</span><span class="sxs-lookup"><span data-stu-id="dc577-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="dc577-108">Utilizzare queste astrazioni anziché `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, perché questo separa i metodi delle implementazioni specifiche di un documento XML in memoria e consente loro di lavorare con le origini dati XML virtuale che espongono `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="dc577-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="dc577-109">**X non** sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una vista XML di un'origine dati o modello di oggetto sottostante.</span><span class="sxs-lookup"><span data-stu-id="dc577-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="dc577-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="dc577-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dc577-111">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dc577-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc577-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc577-112">See Also</span></span>  
 [<span data-ttu-id="dc577-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="dc577-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="dc577-114">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="dc577-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
