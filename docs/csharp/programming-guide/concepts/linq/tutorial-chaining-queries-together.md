---
title: 'Esercitazione: Concatenamento di query (C#)'
ms.date: 07/20/2015
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
ms.openlocfilehash: cab012a6ae618bd731c26bc1a002c144b84d2169
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45609632"
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="36e4b-102">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="36e4b-103">In questa esercitazione viene illustrato il modello di elaborazione correlato al concatenamento di query.</span><span class="sxs-lookup"><span data-stu-id="36e4b-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="36e4b-104">Il concatenamento di query costituisce una parte fondamentale nella scrittura delle trasformazioni funzionali.</span><span class="sxs-lookup"><span data-stu-id="36e4b-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="36e4b-105">È quindi importante comprendere esattamente il funzionamento delle query concatenate.</span><span class="sxs-lookup"><span data-stu-id="36e4b-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="36e4b-106">Questa tecnica viene usata in particolare con le query che elaborano documenti Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="36e4b-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36e4b-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="36e4b-107">In This Section</span></span>  
  
|<span data-ttu-id="36e4b-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="36e4b-108">Topic</span></span>|<span data-ttu-id="36e4b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36e4b-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36e4b-110">Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="36e4b-111">Vengono descritti i concetti di esecuzione posticipata e valutazione lazy.</span><span class="sxs-lookup"><span data-stu-id="36e4b-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|[<span data-ttu-id="36e4b-112">Esempio di esecuzione posticipata (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-112">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)|<span data-ttu-id="36e4b-113">Viene fornito un esempio di esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="36e4b-113">Provides an example of deferred execution.</span></span>|  
|[<span data-ttu-id="36e4b-114">Esempio di concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-114">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)|<span data-ttu-id="36e4b-115">Viene illustrato il funzionamento dell'esecuzione posticipata con le query concatenate.</span><span class="sxs-lookup"><span data-stu-id="36e4b-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|[<span data-ttu-id="36e4b-116">Materializzazione intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-116">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)|<span data-ttu-id="36e4b-117">Viene identificata e illustrata la semantica della materializzazione intermedia.</span><span class="sxs-lookup"><span data-stu-id="36e4b-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|[<span data-ttu-id="36e4b-118">Concatenamento di operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-118">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)|<span data-ttu-id="36e4b-119">Viene descritta la semantica lazy degli operatori di query standard.</span><span class="sxs-lookup"><span data-stu-id="36e4b-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36e4b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36e4b-120">See Also</span></span>

- [<span data-ttu-id="36e4b-121">Trasformazioni funzionali pure di XML (C#)</span><span class="sxs-lookup"><span data-stu-id="36e4b-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
