---
title: Analisi di altre stringhe in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="f6e20-102">Analisi di altre stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="f6e20-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="f6e20-103">Oltre a numerico e <xref:System.DateTime> stringhe, è possibile analizzare le stringhe che rappresentano i tipi di <xref:System.Char>, <xref:System.Boolean>, e <xref:System.Enum> in tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="f6e20-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="f6e20-104">Char</span><span class="sxs-lookup"><span data-stu-id="f6e20-104">Char</span></span>  
 <span data-ttu-id="f6e20-105">Il metodo di analisi statico associato al tipo di dati **Char** è utile per la conversione di una stringa contenente un solo carattere nel valore Unicode corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f6e20-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="f6e20-106">Nell'esempio seguente viene analizzata una stringa in un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="f6e20-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="f6e20-107">Booleano</span><span class="sxs-lookup"><span data-stu-id="f6e20-107">Boolean</span></span>  
 <span data-ttu-id="f6e20-108">Il **booleano** tipo di dati contiene un **analizzare** metodo che è possibile utilizzare per convertire una stringa che rappresenta un valore booleano in una vera e propria **booleano** tipo.</span><span class="sxs-lookup"><span data-stu-id="f6e20-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="f6e20-109">Questo metodo non fa distinzione tra maiuscole e minuscole e consente di analizzare correttamente una stringa contenente "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="f6e20-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="f6e20-110">Il **analizzare** metodo associato il **booleano** tipo consente inoltre di analizzare le stringhe sono racchiusi tra spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="f6e20-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="f6e20-111">Se viene passata qualsiasi altra stringa, un <xref:System.FormatException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f6e20-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="f6e20-112">Nell'esempio di codice viene illustrato come utilizzare il **analizzare** metodo per convertire una stringa in un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="f6e20-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="f6e20-113">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="f6e20-113">Enumeration</span></span>  
 <span data-ttu-id="f6e20-114">È possibile usare il metodo statico **Parse** per inizializzare un tipo di enumerazione per il valore di una stringa.</span><span class="sxs-lookup"><span data-stu-id="f6e20-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="f6e20-115">Questo metodo accetta il tipo di enumerazione che si sta analizzando la stringa da analizzare e un flag booleano facoltativo che indica se è o meno l'analisi tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f6e20-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="f6e20-116">La stringa da analizzare può contenere diversi valori separati da virgole, che possono essere preceduti o seguiti da uno o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="f6e20-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="f6e20-117">Quando la stringa contiene più valori, il valore dell'oggetto restituito è il valore di tutti i valori specificati combinati con un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f6e20-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="f6e20-118">L'esempio seguente usa il **analizzare** metodo per convertire una rappresentazione di stringa in un valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f6e20-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="f6e20-119">Il <xref:System.DayOfWeek> enumerazione viene inizializzata su **giovedì** da una stringa.</span><span class="sxs-lookup"><span data-stu-id="f6e20-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f6e20-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6e20-120">See Also</span></span>  
 [<span data-ttu-id="f6e20-121">Analisi di stringhe</span><span class="sxs-lookup"><span data-stu-id="f6e20-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="f6e20-122">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="f6e20-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="f6e20-123">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="f6e20-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
