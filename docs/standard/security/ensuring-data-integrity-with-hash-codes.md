---
title: Integrità dei dati con codici hash
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16770ea938973372d1d94c628c42d5d5bf10c695
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528552"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="8613f-102">Integrità dei dati con codici hash</span><span class="sxs-lookup"><span data-stu-id="8613f-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="8613f-103">Un valore hash è un valore numerico di lunghezza fissa che identifica in modo univoco i dati.</span><span class="sxs-lookup"><span data-stu-id="8613f-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="8613f-104">I valori hash rappresentano grandi quantità di dati sotto forma di valori numerici molto più piccoli, pertanto vengono usati con le firme digitali.</span><span class="sxs-lookup"><span data-stu-id="8613f-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="8613f-105">È possibile firmare un valore hash in modo più efficiente rispetto alla firma di un valore più grande.</span><span class="sxs-lookup"><span data-stu-id="8613f-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="8613f-106">I valori hash sono anche utili per verificare l'integrità dei dati inviati attraverso canali non sicuri.</span><span class="sxs-lookup"><span data-stu-id="8613f-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="8613f-107">Il valore hash dei dati ricevuti può essere confrontato con il valore hash dei dati inviati per determinare se i dati sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="8613f-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="8613f-108">Questo argomento descrive come generare e verificare codici hash usando le classi nello spazio dei nomi <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8613f-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="8613f-109">Generazione di un hash</span><span class="sxs-lookup"><span data-stu-id="8613f-109">Generating a Hash</span></span>  
 <span data-ttu-id="8613f-110">Le classi hash gestite possono eseguire l'hashing di una matrice di byte o di un oggetto flusso gestito.</span><span class="sxs-lookup"><span data-stu-id="8613f-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="8613f-111">L'esempio seguente usa l'algoritmo hash SHA1 per creare un valore hash per una stringa.</span><span class="sxs-lookup"><span data-stu-id="8613f-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="8613f-112">L'esempio usa la classe <xref:System.Text.UnicodeEncoding> per convertire la stringa in una matrice di byte sottoposti ad hashing tramite la classe <xref:System.Security.Cryptography.SHA1Managed>.</span><span class="sxs-lookup"><span data-stu-id="8613f-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="8613f-113">Il valore hash viene quindi visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="8613f-113">The hash value is then displayed to the console.</span></span>  
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="8613f-114">Questo codice visualizza la stringa seguente nella console:</span><span class="sxs-lookup"><span data-stu-id="8613f-114">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="8613f-115">Verifica di un hash</span><span class="sxs-lookup"><span data-stu-id="8613f-115">Verifying a Hash</span></span>  
 <span data-ttu-id="8613f-116">I dati possono essere confrontati con un valore hash per determinarne l'integrità.</span><span class="sxs-lookup"><span data-stu-id="8613f-116">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="8613f-117">In genere, viene eseguito l'hashing dei dati in un determinato momento e il valore hash viene protetto in un determinato modo.</span><span class="sxs-lookup"><span data-stu-id="8613f-117">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="8613f-118">Successivamente, i dati possono essere sottoposti di nuovo a hashing e confrontati con il valore protetto.</span><span class="sxs-lookup"><span data-stu-id="8613f-118">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="8613f-119">Se i valori hash corrispondono, i dati non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="8613f-119">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="8613f-120">Se i valori hash non corrispondono, i dati sono stati danneggiati.</span><span class="sxs-lookup"><span data-stu-id="8613f-120">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="8613f-121">Affinché questo sistema funzioni, l'hash protetto deve essere crittografato o mantenuto segreto a tutte le parti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="8613f-121">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="8613f-122">L'esempio seguente confronta il valore hash precedente di una stringa con un nuovo valore hash.</span><span class="sxs-lookup"><span data-stu-id="8613f-122">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="8613f-123">L'esempio analizza in ciclo ogni byte dei valori hash ed effettua un confronto.</span><span class="sxs-lookup"><span data-stu-id="8613f-123">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="8613f-124">Se i due valori hash corrispondono, il codice visualizza quanto segue nella console:</span><span class="sxs-lookup"><span data-stu-id="8613f-124">If the two hash values match, this code displays the following to the console:</span></span>  
  
```  
The hash codes match.  
```  
  
 <span data-ttu-id="8613f-125">Se non corrispondono, il codice visualizza quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8613f-125">If they do not match, the code displays the following:</span></span>  
  
```  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="8613f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8613f-126">See also</span></span>

- [<span data-ttu-id="8613f-127">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8613f-127">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
