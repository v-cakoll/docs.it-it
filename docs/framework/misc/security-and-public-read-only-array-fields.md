---
title: Sicurezza e campi di matrice pubblici di sola lettura
description: Leggere il motivo per cui è consigliabile evitare di usare campi di matrice di sola lettura pubblici per definire il comportamento dei limiti o la sicurezza delle applicazioni.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 0a6a82c2c88fe61bd34c0accb831f018cf8702fc
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281433"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="a7fff-103">Sicurezza e campi di matrice pubblici di sola lettura</span><span class="sxs-lookup"><span data-stu-id="a7fff-103">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="a7fff-104">Non usare mai i campi di matrice pubblica di sola lettura dalle librerie gestite per definire il comportamento dei limiti o la sicurezza delle applicazioni perché è possibile modificare i campi di matrice pubblica di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a7fff-104">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7fff-105">Commenti</span><span class="sxs-lookup"><span data-stu-id="a7fff-105">Remarks</span></span>  

<span data-ttu-id="a7fff-106">Alcune classi .NET includono campi pubblici di sola lettura che contengono parametri limite specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="a7fff-106">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="a7fff-107">Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che descrive i caratteri non consentiti in una stringa di percorso file.</span><span class="sxs-lookup"><span data-stu-id="a7fff-107">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="a7fff-108">Molti campi simili sono presenti in .NET.</span><span class="sxs-lookup"><span data-stu-id="a7fff-108">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="a7fff-109">I valori dei campi di sola lettura pubblici come <xref:System.IO.Path.InvalidPathChars> possono essere modificati dal codice o dal codice che condivide il dominio applicazione del codice.</span><span class="sxs-lookup"><span data-stu-id="a7fff-109">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="a7fff-110">Non usare campi di matrice pubblica di sola lettura come questo per definire il comportamento dei limiti delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a7fff-110">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="a7fff-111">In tal caso, il codice dannoso può modificare le definizioni dei limiti e usare il codice in modi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="a7fff-111">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="a7fff-112">Nella versione 2,0 e successive del .NET Framework, è consigliabile usare metodi che restituiscono una nuova matrice anziché usare campi di matrice pubblici.</span><span class="sxs-lookup"><span data-stu-id="a7fff-112">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="a7fff-113">Ad esempio, invece di usare il <xref:System.IO.Path.InvalidPathChars> campo, è necessario usare il <xref:System.IO.Path.GetInvalidPathChars%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="a7fff-113">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="a7fff-114">Si noti che i tipi di .NET Framework non usano i campi pubblici per definire i tipi di limite internamente.</span><span class="sxs-lookup"><span data-stu-id="a7fff-114">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="a7fff-115">Il .NET Framework utilizza invece campi privati distinti.</span><span class="sxs-lookup"><span data-stu-id="a7fff-115">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="a7fff-116">La modifica dei valori di questi campi pubblici non comporta la modifica del comportamento dei tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a7fff-116">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fff-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7fff-117">See also</span></span>

- [<span data-ttu-id="a7fff-118">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="a7fff-118">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
