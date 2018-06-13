---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0110bb42775d8a5df9ca268b35db3abaffec84f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392629"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="6f1d9-102">Sicurezza e campi di matrice pubblici di sola lettura</span><span class="sxs-lookup"><span data-stu-id="6f1d9-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="6f1d9-103">Non utilizzare mai i campi di matrice pubblici di sola lettura da librerie gestite per definire il comportamento del limite o la sicurezza delle applicazioni, poiché i campi di matrice pubblici di sola lettura possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f1d9-104">Note</span><span class="sxs-lookup"><span data-stu-id="6f1d9-104">Remarks</span></span>  
 <span data-ttu-id="6f1d9-105">Alcune classi di .NET framework includono campi pubblici di sola lettura che contengono parametri limiti specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="6f1d9-106">Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che contiene i caratteri non consentiti in una stringa di percorso del file.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="6f1d9-107">Numero di campi simili è presenti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="6f1d9-108">I valori dei campi pubblici di sola lettura come <xref:System.IO.Path.InvalidPathChars> può essere modificato da codice che condivide il dominio dell'applicazione o il codice.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="6f1d9-109">Utilizzare i campi di matrice pubblici di sola lettura simile al seguente per definire il comportamento del limite delle applicazioni non.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="6f1d9-110">In caso contrario, codice dannoso può modificare le definizioni di limite e utilizzare il codice in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="6f1d9-111">Nella versione 2.0 e versioni successive di .NET Framework, è necessario utilizzare metodi che restituiscono una nuova matrice anziché utilizzare i campi di matrice pubblici.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="6f1d9-112">Ad esempio, anziché utilizzare il <xref:System.IO.Path.InvalidPathChars> campo, è consigliabile utilizzare il <xref:System.IO.Path.GetInvalidPathChars%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="6f1d9-113">Si noti che i tipi .NET Framework non utilizzano i campi pubblici per definire i tipi di limite internamente.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="6f1d9-114">.NET Framework utilizza invece campi privati separati.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="6f1d9-115">Modifica dei valori di questi campi pubblici non modifica il comportamento dei tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f1d9-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1d9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f1d9-116">See Also</span></span>  
 [<span data-ttu-id="6f1d9-117">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="6f1d9-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
