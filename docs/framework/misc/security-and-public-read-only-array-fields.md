---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 2df4acc0606e4fe8fccee4a8acc6ab744dcbbb71
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452708"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="1f870-102">Sicurezza e campi di matrice pubblici di sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f870-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="1f870-103">Non usare mai i campi di matrice pubblica di sola lettura dalle librerie gestite per definire il comportamento dei limiti o la sicurezza delle applicazioni perché è possibile modificare i campi di matrice pubblica di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1f870-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f870-104">Note</span><span class="sxs-lookup"><span data-stu-id="1f870-104">Remarks</span></span>  

<span data-ttu-id="1f870-105">Alcune classi .NET includono campi pubblici di sola lettura che contengono parametri limite specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="1f870-105">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="1f870-106">Ad esempio, il campo <xref:System.IO.Path.InvalidPathChars> è una matrice che descrive i caratteri non consentiti in una stringa di percorso file.</span><span class="sxs-lookup"><span data-stu-id="1f870-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="1f870-107">Molti campi simili sono presenti in .NET.</span><span class="sxs-lookup"><span data-stu-id="1f870-107">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="1f870-108">I valori dei campi di sola lettura pubblici come <xref:System.IO.Path.InvalidPathChars> possono essere modificati dal codice o dal codice che condivide il dominio applicazione del codice.</span><span class="sxs-lookup"><span data-stu-id="1f870-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="1f870-109">Non usare campi di matrice pubblica di sola lettura come questo per definire il comportamento dei limiti delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1f870-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="1f870-110">In tal caso, il codice dannoso può modificare le definizioni dei limiti e usare il codice in modi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="1f870-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="1f870-111">Nella versione 2,0 e successive del .NET Framework, è consigliabile usare metodi che restituiscono una nuova matrice anziché usare campi di matrice pubblici.</span><span class="sxs-lookup"><span data-stu-id="1f870-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="1f870-112">Ad esempio, invece di usare il campo <xref:System.IO.Path.InvalidPathChars>, è necessario usare il metodo <xref:System.IO.Path.GetInvalidPathChars%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f870-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="1f870-113">Si noti che i tipi di .NET Framework non usano i campi pubblici per definire i tipi di limite internamente.</span><span class="sxs-lookup"><span data-stu-id="1f870-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="1f870-114">Il .NET Framework utilizza invece campi privati distinti.</span><span class="sxs-lookup"><span data-stu-id="1f870-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="1f870-115">La modifica dei valori di questi campi pubblici non comporta la modifica del comportamento dei tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f870-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f870-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f870-116">See also</span></span>

- [<span data-ttu-id="1f870-117">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="1f870-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
