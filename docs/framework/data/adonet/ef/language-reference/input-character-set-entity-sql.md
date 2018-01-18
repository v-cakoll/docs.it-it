---
title: Set di caratteri di input (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d75d8c96d1cc028bed8beea16e2728e5654a12c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="200cc-102">Set di caratteri di input (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="200cc-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="200cc-103"> accetta i caratteri Unicode con codifica UTF-16.</span><span class="sxs-lookup"><span data-stu-id="200cc-103"> accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="200cc-104">I valori letterali stringa possono contenere qualsiasi carattere UTF-16 racchiuso tra virgolette singole.</span><span class="sxs-lookup"><span data-stu-id="200cc-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="200cc-105">Ad esempio, N'文字列リテラル'.</span><span class="sxs-lookup"><span data-stu-id="200cc-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="200cc-106">Quando i valori letterali stringa vengono confrontati, vengono usati i valori UTF-16 originali.</span><span class="sxs-lookup"><span data-stu-id="200cc-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="200cc-107">N'ABC, ad esempio, è diverso nelle tabelle codici giapponese e latina.</span><span class="sxs-lookup"><span data-stu-id="200cc-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="200cc-108">I commenti possono contenere qualsiasi carattere UTF-16.</span><span class="sxs-lookup"><span data-stu-id="200cc-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="200cc-109">Gli identificatori preceduti da un carattere di escape possono contenere qualsiasi carattere UTF-16 racchiuso tra parentesi quadre,</span><span class="sxs-lookup"><span data-stu-id="200cc-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="200cc-110">Ad esempio, [エスケープされた識別子].</span><span class="sxs-lookup"><span data-stu-id="200cc-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="200cc-111">Il confronto di identificatori UTF-16 che usano caratteri di escape è senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="200cc-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> <span data-ttu-id="200cc-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le versioni delle lettere che hanno lo stesso aspetto ma che provengono da tabelle codici diverse vengono gestite come caratteri differenti.</span><span class="sxs-lookup"><span data-stu-id="200cc-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="200cc-113">Le lettere [ABC], ad esempio, equivalgono alle lettere [abc] se i caratteri corrispondenti appartengono alla stessa tabella codici.</span><span class="sxs-lookup"><span data-stu-id="200cc-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="200cc-114">Se, tuttavia, gli stessi due identificatori appartengono a tabelle codici differenti, non sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="200cc-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="200cc-115">Lo spazio vuoto è qualsiasi carattere di spazio vuoto UTF-16.</span><span class="sxs-lookup"><span data-stu-id="200cc-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="200cc-116">Una nuova riga è qualsiasi carattere di nuova riga UTF-16 normalizzato.</span><span class="sxs-lookup"><span data-stu-id="200cc-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="200cc-117">'\n' e '\r\n' sono ad esempio considerati caratteri di nuova riga, mentre '\r' no.</span><span class="sxs-lookup"><span data-stu-id="200cc-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="200cc-118">Le parole chiave, le espressioni e la punteggiatura possono essere qualsiasi carattere UTF-16 normalizzato in latino.</span><span class="sxs-lookup"><span data-stu-id="200cc-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="200cc-119">SELECT in una tabella codici giapponese è, ad esempio, una parola chiave valida.</span><span class="sxs-lookup"><span data-stu-id="200cc-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="200cc-120">Le parole chiave, le espressioni e la punteggiatura possono essere solo caratteri latini.</span><span class="sxs-lookup"><span data-stu-id="200cc-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="200cc-121">`SELECT` in una tabella codici giapponese non è una parola chiave.</span><span class="sxs-lookup"><span data-stu-id="200cc-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="200cc-122">+, -, \*, /, =, () ', [,] e qualsiasi altro costrutto di linguaggio non citato possono essere solo caratteri latini.</span><span class="sxs-lookup"><span data-stu-id="200cc-122">+, -, \*, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="200cc-123">Gli identificatori semplici possono essere solo caratteri latini.</span><span class="sxs-lookup"><span data-stu-id="200cc-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="200cc-124">Questo consente di evitare l'ambiguità durante il confronto, poiché vengono confrontati i valori originali.</span><span class="sxs-lookup"><span data-stu-id="200cc-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="200cc-125">ABC sarebbe ad esempio diverso nelle tabelle codici giapponese e latina.</span><span class="sxs-lookup"><span data-stu-id="200cc-125">For example, ABC would be different in in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200cc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="200cc-126">See Also</span></span>  
 [<span data-ttu-id="200cc-127">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="200cc-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
