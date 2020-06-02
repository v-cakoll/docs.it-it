---
title: Utilizzo di System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 07828219f2e17be925d060fa3bb33a9209ecb62b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291669"
---
# <a name="systemxml-usage"></a><span data-ttu-id="5b39e-102">Utilizzo di System.Xml</span><span class="sxs-lookup"><span data-stu-id="5b39e-102">System.Xml Usage</span></span>
<span data-ttu-id="5b39e-103">In questa sezione viene descritto l'utilizzo di diversi tipi che risiedono negli <xref:System.Xml?displayProperty=nameWithType> spazi dei nomi che possono essere utilizzati per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="5b39e-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="5b39e-104">❌Non usare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="5b39e-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="5b39e-105">Preferire l'utilizzo di istanze dei <xref:System.Xml.XPath.IXPathNavigable> <xref:System.Xml.XmlReader> <xref:System.Xml.XmlWriter> sottotipi,, o di <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="5b39e-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="5b39e-106">`XmlNode`e `XmlDocument` non sono progettate per l'esposizione in API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="5b39e-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="5b39e-107">✔️ utilizzano `XmlReader` `IXPathNavigable` i sottotipi, o di `XNode` come input o output di membri che accettano o restituiscono XML.</span><span class="sxs-lookup"><span data-stu-id="5b39e-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="5b39e-108">Utilizzare queste astrazioni anziché `XmlDocument` , `XmlNode` o, <xref:System.Xml.XPath.XPathDocument> perché questo separa i metodi da implementazioni specifiche di un documento XML in memoria e consente loro di utilizzare origini dati XML virtuali che espongono `XNode` , `XmlReader` o <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="5b39e-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="5b39e-109">❌NON eseguire la sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una visualizzazione XML di un modello a oggetti sottostante o di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5b39e-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="5b39e-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="5b39e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5b39e-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5b39e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5b39e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b39e-112">See also</span></span>

- [<span data-ttu-id="5b39e-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="5b39e-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="5b39e-114">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="5b39e-114">Usage Guidelines</span></span>](usage-guidelines.md)
