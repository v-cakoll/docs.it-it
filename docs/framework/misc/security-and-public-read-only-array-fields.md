---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19b5ad73150697c1442056642a1b11d504ecc426
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61869746"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="658ed-102">Sicurezza e campi di matrice pubblici di sola lettura</span><span class="sxs-lookup"><span data-stu-id="658ed-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="658ed-103">Consente di utilizzare mai i campi di matrice pubblica di sola lettura dalla librerie gestite per definire il comportamento del limite o la sicurezza delle applicazioni perché i campi di matrice pubblica di sola lettura possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="658ed-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="658ed-104">Note</span><span class="sxs-lookup"><span data-stu-id="658ed-104">Remarks</span></span>  
 <span data-ttu-id="658ed-105">Alcune classi di .NET framework includono campi pubblici di sola lettura che contengono parametri di limiti specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="658ed-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="658ed-106">Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che descrive i caratteri non consentiti in una stringa di percorso di file.</span><span class="sxs-lookup"><span data-stu-id="658ed-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="658ed-107">Numero di campi simili è presenti in tutto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="658ed-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="658ed-108">I valori dei campi pubblici di sola lettura come <xref:System.IO.Path.InvalidPathChars> può essere modificato dal codice o dal codice che condivide il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="658ed-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="658ed-109">Non si utilizzino i campi di matrice pubblica di sola lettura simile al seguente per definire il comportamento del limite delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="658ed-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="658ed-110">In caso contrario codice dannoso può modificare le definizioni dei limiti e usare il codice in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="658ed-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="658ed-111">Nella versione 2.0 e versioni successive di .NET Framework, è necessario usare i metodi che restituiscono una nuova matrice invece di usare i campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="658ed-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="658ed-112">Ad esempio, invece di usare la <xref:System.IO.Path.InvalidPathChars> campo, è consigliabile usare il <xref:System.IO.Path.GetInvalidPathChars%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="658ed-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="658ed-113">Si noti che i tipi di .NET Framework non utilizzano i campi pubblici per definire tipi di limite internamente.</span><span class="sxs-lookup"><span data-stu-id="658ed-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="658ed-114">Al contrario, .NET Framework Usa separati campi privati.</span><span class="sxs-lookup"><span data-stu-id="658ed-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="658ed-115">Modifica dei valori di questi campi pubblici non modifica il comportamento dei tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="658ed-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658ed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="658ed-116">See also</span></span>

- [<span data-ttu-id="658ed-117">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="658ed-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
