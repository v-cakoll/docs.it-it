---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910729"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="8cc54-102">Sicurezza e campi di matrice pubblici di sola lettura</span><span class="sxs-lookup"><span data-stu-id="8cc54-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="8cc54-103">Non usare mai i campi di matrice pubblica di sola lettura dalle librerie gestite per definire il comportamento dei limiti o la sicurezza delle applicazioni perché è possibile modificare i campi di matrice pubblica di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8cc54-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cc54-104">Note</span><span class="sxs-lookup"><span data-stu-id="8cc54-104">Remarks</span></span>  
 <span data-ttu-id="8cc54-105">Alcune classi di .NET Framework includono campi pubblici di sola lettura che contengono parametri limite specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="8cc54-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="8cc54-106">Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che descrive i caratteri non consentiti in una stringa di percorso file.</span><span class="sxs-lookup"><span data-stu-id="8cc54-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="8cc54-107">In .NET Framework sono presenti molti campi simili.</span><span class="sxs-lookup"><span data-stu-id="8cc54-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="8cc54-108">I valori dei campi di sola lettura pubblici come <xref:System.IO.Path.InvalidPathChars> possono essere modificati dal codice o dal codice che condivide il dominio applicazione del codice.</span><span class="sxs-lookup"><span data-stu-id="8cc54-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="8cc54-109">Non usare campi di matrice pubblica di sola lettura come questo per definire il comportamento dei limiti delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8cc54-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="8cc54-110">In tal caso, il codice dannoso può modificare le definizioni dei limiti e usare il codice in modi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="8cc54-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="8cc54-111">Nella versione 2,0 e successive del .NET Framework, è consigliabile usare metodi che restituiscono una nuova matrice anziché usare campi di matrice pubblici.</span><span class="sxs-lookup"><span data-stu-id="8cc54-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="8cc54-112">Ad esempio, invece di usare il <xref:System.IO.Path.InvalidPathChars> campo, è necessario usare il <xref:System.IO.Path.GetInvalidPathChars%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8cc54-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="8cc54-113">Si noti che i tipi di .NET Framework non usano i campi pubblici per definire i tipi di limite internamente.</span><span class="sxs-lookup"><span data-stu-id="8cc54-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="8cc54-114">Il .NET Framework utilizza invece campi privati distinti.</span><span class="sxs-lookup"><span data-stu-id="8cc54-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="8cc54-115">La modifica dei valori di questi campi pubblici non comporta la modifica del comportamento dei tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8cc54-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc54-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cc54-116">See also</span></span>

- [<span data-ttu-id="8cc54-117">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="8cc54-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
