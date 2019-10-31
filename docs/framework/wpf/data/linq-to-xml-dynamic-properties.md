---
title: Informazioni di riferimento sulle proprietà dinamiche LINQ to XML
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 48b51e92eb78786b2cc189e3e7daa00875b41585
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197047"
---
# <a name="linq-to-xml-dynamic-properties"></a><span data-ttu-id="3c723-102">Proprietà dinamiche di LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3c723-102">LINQ to XML dynamic properties</span></span>

<span data-ttu-id="3c723-103">Contenuto della sezione vengono fornite informazioni di riferimento relative alle proprietà dinamiche di LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="3c723-103">This section provides reference information about the dynamic properties in LINQ to XML.</span></span> <span data-ttu-id="3c723-104">In particolare, queste proprietà vengono esposte dalle classi <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>, incluse nello spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="3c723-104">Specifically, these properties are exposed by the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, which are in the <xref:System.Xml.Linq> namespace.</span></span>

<span data-ttu-id="3c723-105">Come illustrato nell'argomento [Panoramica del data binding di WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), ogni proprietà dinamica è equivalente a una proprietà o a un metodo pubblico standard della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="3c723-105">As explained in the topic [Overview of WPF data binding with LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), each of the dynamic properties is equivalent to a standard public property or method in the same class.</span></span> <span data-ttu-id="3c723-106">Questi membri standard devono essere usati per la maggior parte degli scopi. Le proprietà dinamiche vengono fornite specificamente per gli scenari di associazione dati LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="3c723-106">These standard members should be used for most purposes; dynamic properties are provided specifically for LINQ to XML data binding scenarios.</span></span> <span data-ttu-id="3c723-107">Per altre informazioni sui membri standard di queste classi, vedere gli argomenti di riferimento <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3c723-107">For more information about the standard members of these classes, see the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> reference topics.</span></span>

<span data-ttu-id="3c723-108">Relativamente ai valori risolti, le proprietà dinamiche descritte in questa sezione rientrano in due categorie:</span><span class="sxs-lookup"><span data-stu-id="3c723-108">With respect to their resolved values, the dynamic properties in this section fall into two categories:</span></span>

- <span data-ttu-id="3c723-109">Proprietà semplici, ad esempio le proprietà `Value` nelle classi <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>, che vengono risolte in un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="3c723-109">Simple ones, such as the `Value` properties in the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, that resolve to a single value.</span></span>

- <span data-ttu-id="3c723-110">Valori indicizzati, ad esempio le proprietà [Elements](elements-xelement-dynamic-property.md) e [Descendants](descendants-xelement-dynamic-property.md) di <xref:System.Xml.Linq.XElement>, che vengono risolti in un tipo di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="3c723-110">Indexed values, such as the [Elements](elements-xelement-dynamic-property.md) and [Descendants](descendants-xelement-dynamic-property.md) properties of <xref:System.Xml.Linq.XElement>, that resolve into an indexer type.</span></span> <span data-ttu-id="3c723-111">Affinché i tipi di indicizzatori vengano risolti nel valore o nella raccolta desiderata, è necessario passare un parametro di nome espanso.</span><span class="sxs-lookup"><span data-stu-id="3c723-111">For indexer types to be resolved to the desired value or collection, an expanded name parameter must be passed to them.</span></span>

<span data-ttu-id="3c723-112">Tutte le proprietà dinamiche che restituiscono un valore indicizzato di tipo <xref:System.Collections.Generic.IEnumerable%601> usano l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="3c723-112">All the dynamic properties that return an indexed value of type <xref:System.Collections.Generic.IEnumerable%601> use deferred execution.</span></span> <span data-ttu-id="3c723-113">Per altre informazioni sull'esecuzione posticipata, vedere [Introduzione alle query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3c723-113">For more information about deferred execution, see [Introduction to LINQ queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="reference"></a><span data-ttu-id="3c723-114">Reference</span><span class="sxs-lookup"><span data-stu-id="3c723-114">Reference</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="3c723-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c723-115">See also</span></span>

- [<span data-ttu-id="3c723-116">Associazione dati WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3c723-116">WPF data binding with LINQ to XML</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="3c723-117">Panoramica del data binding WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3c723-117">WPF data binding with LINQ to XML overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="3c723-118">Introduzione alle query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="3c723-118">Introduction to LINQ queries (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
