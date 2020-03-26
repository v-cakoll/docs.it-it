---
title: Regole di confronto
ms.date: 12/13/2019
description: Scopri come creare una sequenza di confronto personalizzata.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506541"
---
# <a name="collation"></a><span data-ttu-id="a4a98-103">Regole di confronto</span><span class="sxs-lookup"><span data-stu-id="a4a98-103">Collation</span></span>

<span data-ttu-id="a4a98-104">Le sequenze di confronto vengono utilizzate da SQLite quando si confrontano i valori TEXT per determinare l'ordine e l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="a4a98-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="a4a98-105">È possibile specificare le regole di confronto da utilizzare quando si creano colonne o per ogni operazione nelle query SQL.</span><span class="sxs-lookup"><span data-stu-id="a4a98-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="a4a98-106">SQLite include tre sequenze di confronto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4a98-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="a4a98-107">Regole di confronto</span><span class="sxs-lookup"><span data-stu-id="a4a98-107">Collation</span></span> | <span data-ttu-id="a4a98-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4a98-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="a4a98-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="a4a98-109">RTRIM</span></span>     | <span data-ttu-id="a4a98-110">Ignora gli spazi vuoti finali</span><span class="sxs-lookup"><span data-stu-id="a4a98-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="a4a98-111">NESSUN CASO</span><span class="sxs-lookup"><span data-stu-id="a4a98-111">NOCASE</span></span>    | <span data-ttu-id="a4a98-112">Senza distinzione tra maiuscole e minuscole per i caratteri ASCII dalla A alla z</span><span class="sxs-lookup"><span data-stu-id="a4a98-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="a4a98-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="a4a98-113">BINARY</span></span>    | <span data-ttu-id="a4a98-114">Sensitive.</span><span class="sxs-lookup"><span data-stu-id="a4a98-114">Case-sensitive.</span></span> <span data-ttu-id="a4a98-115">Confronta direttamente i byte</span><span class="sxs-lookup"><span data-stu-id="a4a98-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="a4a98-116">Regole di confronto personalizzate</span><span class="sxs-lookup"><span data-stu-id="a4a98-116">Custom collation</span></span>

<span data-ttu-id="a4a98-117">È inoltre possibile definire sequenze di confronto personalizzate o <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>eseguire l'override di quelle incorporate utilizzando .</span><span class="sxs-lookup"><span data-stu-id="a4a98-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="a4a98-118">Nell'esempio seguente viene illustrato l'override delle regole di confronto NOCASE per supportare i caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a4a98-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="a4a98-119">Il [codice di esempio completo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) è disponibile su GitHub.The full sample code is available on GitHub.</span><span class="sxs-lookup"><span data-stu-id="a4a98-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="a4a98-120">Like (operatore)</span><span class="sxs-lookup"><span data-stu-id="a4a98-120">Like operator</span></span>

<span data-ttu-id="a4a98-121">L'operatore LIKE in SQLite non rispetta le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="a4a98-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="a4a98-122">L'implementazione predefinita ha la stessa semantica delle regole di confronto NOCASE.</span><span class="sxs-lookup"><span data-stu-id="a4a98-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="a4a98-123">È solo senza distinzione tra maiuscole e minuscole per i caratteri ASCII dalla A alla z.</span><span class="sxs-lookup"><span data-stu-id="a4a98-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="a4a98-124">È possibile rendere facilmente l'operatore LIKE tra maiuscole e minuscole utilizzando la seguente istruzione pragma:</span><span class="sxs-lookup"><span data-stu-id="a4a98-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="a4a98-125">Vedere [Funzioni definite dall'utente](user-defined-functions.md) per informazioni dettagliate sull'override dell'implementazione dell'operatore LIKE.</span><span class="sxs-lookup"><span data-stu-id="a4a98-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4a98-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4a98-126">See also</span></span>

* [<span data-ttu-id="a4a98-127">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="a4a98-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="a4a98-128">Sintassi SQL</span><span class="sxs-lookup"><span data-stu-id="a4a98-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
