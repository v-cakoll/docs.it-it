---
title: Collation
ms.date: 12/13/2019
description: Informazioni su come creare una sequenza di ordinamento personalizzata.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447027"
---
# <a name="collation"></a><span data-ttu-id="14acc-103">Collation</span><span class="sxs-lookup"><span data-stu-id="14acc-103">Collation</span></span>

<span data-ttu-id="14acc-104">Le sequenze di confronto vengono usate da SQLite quando si confrontano i valori di testo per determinare l'ordine e l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="14acc-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="14acc-105">È possibile specificare le regole di confronto da utilizzare per la creazione di colonne o per operazione nelle query SQL.</span><span class="sxs-lookup"><span data-stu-id="14acc-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="14acc-106">SQLite include tre sequenze di confronto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="14acc-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="14acc-107">Collation</span><span class="sxs-lookup"><span data-stu-id="14acc-107">Collation</span></span> | <span data-ttu-id="14acc-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14acc-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="14acc-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="14acc-109">RTRIM</span></span>     | <span data-ttu-id="14acc-110">Ignora lo spazio vuoto finale</span><span class="sxs-lookup"><span data-stu-id="14acc-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="14acc-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="14acc-111">NOCASE</span></span>    | <span data-ttu-id="14acc-112">Senza distinzione tra maiuscole e minuscole per i caratteri ASCII A-Z</span><span class="sxs-lookup"><span data-stu-id="14acc-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="14acc-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="14acc-113">BINARY</span></span>    | <span data-ttu-id="14acc-114">Distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="14acc-114">Case-sensitive.</span></span> <span data-ttu-id="14acc-115">Confronta i byte direttamente</span><span class="sxs-lookup"><span data-stu-id="14acc-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="14acc-116">Regole di confronto personalizzate</span><span class="sxs-lookup"><span data-stu-id="14acc-116">Custom collation</span></span>

<span data-ttu-id="14acc-117">È anche possibile definire sequenze di fascicolazione personalizzate oppure eseguire l'override di quelle predefinite usando <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span><span class="sxs-lookup"><span data-stu-id="14acc-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="14acc-118">Nell'esempio seguente viene illustrato come eseguire l'override delle regole di confronto nocase per supportare i caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="14acc-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="14acc-119">Il [codice di esempio completo](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) è disponibile in GitHub.</span><span class="sxs-lookup"><span data-stu-id="14acc-119">The [full sample code](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="14acc-120">Like (operatore)</span><span class="sxs-lookup"><span data-stu-id="14acc-120">Like operator</span></span>

<span data-ttu-id="14acc-121">L'operatore LIKE in SQLite non rispetta le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="14acc-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="14acc-122">L'implementazione predefinita ha la stessa semantica delle regole di confronto nocase.</span><span class="sxs-lookup"><span data-stu-id="14acc-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="14acc-123">Non fa distinzione tra maiuscole e minuscole per i caratteri ASCII da A A Z.</span><span class="sxs-lookup"><span data-stu-id="14acc-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="14acc-124">È possibile rendere facilmente l'operatore LIKE con distinzione tra maiuscole e minuscole usando l'istruzione pragma seguente:</span><span class="sxs-lookup"><span data-stu-id="14acc-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="14acc-125">Per informazioni dettagliate sull'override dell'implementazione dell'operatore LIKE, vedere [funzioni definite dall'utente](user-defined-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="14acc-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="14acc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14acc-126">See also</span></span>

* [<span data-ttu-id="14acc-127">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="14acc-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="14acc-128">Sintassi SQL</span><span class="sxs-lookup"><span data-stu-id="14acc-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
