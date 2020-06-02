---
title: Analisi di altre stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: a3503e0e499c6010fcc3d8669fa5c1eaf2dbf570
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277544"
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="f6b15-102">Analisi di altre stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="f6b15-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="f6b15-103">Oltre alle stringhe numeriche e<xref:System.DateTime> è possibile analizzare le stringhe che rappresentano i tipi <xref:System.Char>, <xref:System.Boolean> ed <xref:System.Enum> in tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="f6b15-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="f6b15-104">Char</span><span class="sxs-lookup"><span data-stu-id="f6b15-104">Char</span></span>  
 <span data-ttu-id="f6b15-105">Il metodo di analisi statico associato al tipo di dati **Char** è utile per la conversione di una stringa contenente un solo carattere nel valore Unicode corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f6b15-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="f6b15-106">Nell'esempio seguente viene analizzata una stringa in un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="f6b15-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="f6b15-107">Boolean</span><span class="sxs-lookup"><span data-stu-id="f6b15-107">Boolean</span></span>  
 <span data-ttu-id="f6b15-108">Il tipo di dati **Boolean** contiene un metodo **Parse** che può essere usato per convertire una stringa che rappresenta un valore booleano in un vero e proprio tipo **Boolean**.</span><span class="sxs-lookup"><span data-stu-id="f6b15-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="f6b15-109">Questo metodo non fa distinzione tra maiuscole e minuscole e consente di analizzare correttamente una stringa contenente "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="f6b15-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="f6b15-110">Il metodo **Parse** associato al tipo **Boolean** consente anche di analizzare stringhe precedute e seguite da spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="f6b15-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="f6b15-111">Se viene passata qualsiasi altra stringa, viene generata un'eccezione <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="f6b15-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="f6b15-112">Nell'esempio di codice seguente viene usato il metodo **Parse** per convertire una stringa in un valore di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="f6b15-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="f6b15-113">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="f6b15-113">Enumeration</span></span>  
 <span data-ttu-id="f6b15-114">È possibile usare il metodo statico **Parse** per inizializzare un tipo di enumerazione per il valore di una stringa.</span><span class="sxs-lookup"><span data-stu-id="f6b15-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="f6b15-115">Questo metodo accetta il tipo di enumerazione che si sta analizzando, la stringa da analizzare e un flag Boolean facoltativo che indica se l'analisi fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f6b15-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="f6b15-116">La stringa da analizzare può contenere diversi valori separati da virgole, che possono essere preceduti o seguiti da uno o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="f6b15-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="f6b15-117">Quando la stringa contiene più valori, il valore dell'oggetto restituito è il valore di tutti i valori specificati combinati con un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f6b15-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="f6b15-118">Nell'esempio seguente viene usato il metodo **Parse** per convertire una rappresentazione di stringa in un valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f6b15-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="f6b15-119">L'enumerazione <xref:System.DayOfWeek> viene inizializzata su **Thursday** da una stringa.</span><span class="sxs-lookup"><span data-stu-id="f6b15-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f6b15-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6b15-120">See also</span></span>

- [<span data-ttu-id="f6b15-121">Analisi di stringhe</span><span class="sxs-lookup"><span data-stu-id="f6b15-121">Parsing Strings</span></span>](parsing-strings.md)
- [<span data-ttu-id="f6b15-122">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="f6b15-122">Formatting Types</span></span>](formatting-types.md)
- [<span data-ttu-id="f6b15-123">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="f6b15-123">Type Conversion in the .NET</span></span>](type-conversion.md)
