---
title: Come analizzare una stringa (C#)
description: Informazioni su come analizzare una stringa per creare un albero XML in C#. Informazioni su come accedere a dati specifici nel codice XML analizzato.
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: a4664e090b6a44c52c519e61b66ccdc5d59a71f1
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104809"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="fa606-104">Come analizzare una stringa (C#)</span><span class="sxs-lookup"><span data-stu-id="fa606-104">How to parse a string (C#)</span></span>

<span data-ttu-id="fa606-105">Questo argomento illustra come analizzare una stringa per creare una struttura ad albero XML in C#.</span><span class="sxs-lookup"><span data-stu-id="fa606-105">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="fa606-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa606-106">Example</span></span>

<span data-ttu-id="fa606-107">Il codice C# seguente illustra come analizzare una stringa XML:</span><span class="sxs-lookup"><span data-stu-id="fa606-107">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="fa606-108">Il `Contacts` nodo radice ha due `Contact` nodi.</span><span class="sxs-lookup"><span data-stu-id="fa606-108">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="fa606-109">Per accedere ad alcuni dati specifici nel codice XML analizzato, usare il metodo [XElement. Elements ()](xref:System.Xml.Linq.XContainer.Elements) , che in questo caso restituisce gli elementi figlio del `Contacts` nodo radice.</span><span class="sxs-lookup"><span data-stu-id="fa606-109">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="fa606-110">Nell'esempio seguente il primo nodo viene stampato nella `Contact` console:</span><span class="sxs-lookup"><span data-stu-id="fa606-110">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="fa606-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa606-111">See also</span></span>

- [<span data-ttu-id="fa606-112">Come trovare un elemento con un attributo specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="fa606-112">How to find an element with a specific attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
