---
title: Utilizzo di System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c3eb01e1050bc78d2b31de19a8a728af92777e8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863387"
---
# <a name="systemxml-usage"></a><span data-ttu-id="442b5-102">Utilizzo di System.Xml</span><span class="sxs-lookup"><span data-stu-id="442b5-102">System.Xml Usage</span></span>
<span data-ttu-id="442b5-103">Questa sezione illustra l'utilizzo dei vari tipi che si trovano <xref:System.Xml?displayProperty=nameWithType> gli spazi dei nomi che può essere utilizzato per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="442b5-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="442b5-104">**X DO NOT** usare <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> per rappresentare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="442b5-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="442b5-105">Preferire l'utilizzo di istanze di <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o sottotipi di <xref:System.Xml.Linq.XNode> invece.</span><span class="sxs-lookup"><span data-stu-id="442b5-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="442b5-106">`XmlNode` e `XmlDocument` non sono progettati per l'esposizione delle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="442b5-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="442b5-107">**✓ DO** usare `XmlReader`, `IXPathNavigable`, o sottotipi di `XNode` come input o output di membri che accettano o restituiscono XML.</span><span class="sxs-lookup"><span data-stu-id="442b5-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="442b5-108">Usare queste astrazioni anziché `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, in quanto ciò consente di disaccoppiare i metodi da implementazioni specifiche di un documento XML in memoria e consente loro di lavorare con le origini dati XML virtuale che espongono `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="442b5-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="442b5-109">**X DO NOT** sottoclasse `XmlDocument` se si desidera creare un tipo che rappresenta una vista XML di un'origine dati o modello di oggetto sottostante.</span><span class="sxs-lookup"><span data-stu-id="442b5-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="442b5-110">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="442b5-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="442b5-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="442b5-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="442b5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="442b5-112">See also</span></span>

- [<span data-ttu-id="442b5-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="442b5-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="442b5-114">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="442b5-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
