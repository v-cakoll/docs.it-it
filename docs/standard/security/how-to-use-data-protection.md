---
title: 'Procedura: utilizzare la protezione dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 0efd677f11189b28b8efc184c04b30a047ab942b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706032"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="71757-102">Procedura: utilizzare la protezione dati</span><span class="sxs-lookup"><span data-stu-id="71757-102">How to: Use Data Protection</span></span>
<span data-ttu-id="71757-103">.NET Framework fornisce l'accesso a Data Protection API (DPAPI), che permette di crittografare dati usando informazioni dell'account utente o del computer corrente.</span><span class="sxs-lookup"><span data-stu-id="71757-103">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="71757-104">L'uso di DPAPI permette di attenuare il problema complesso correlato alla generazione e all'archiviazione esplicite di una chiave crittografica.</span><span class="sxs-lookup"><span data-stu-id="71757-104">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="71757-105">Usare la classe <xref:System.Security.Cryptography.ProtectedMemory> per crittografare una matrice di byte in memoria.</span><span class="sxs-lookup"><span data-stu-id="71757-105">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="71757-106">Questa funzionalità è disponibile nei sistemi operativi Microsoft Windows XP e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="71757-106">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="71757-107">È possibile specificare che la memoria crittografata dal processo corrente può essere decrittografata solo dal processo corrente stesso, da tutti i processi o dallo stesso contesto utente.</span><span class="sxs-lookup"><span data-stu-id="71757-107">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="71757-108">Vedere l'enumerazione <xref:System.Security.Cryptography.MemoryProtectionScope> per una descrizione dettagliata delle opzioni di <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="71757-108">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="71757-109">Usare la classe <xref:System.Security.Cryptography.ProtectedData> per crittografare una copia di una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="71757-109">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="71757-110">Questa funzionalità è disponibile nei sistemi operativi Microsoft Windows 2000 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="71757-110">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="71757-111">È possibile specificare che i dati crittografati dall'account utente corrente possono essere decrittografati solo dallo stesso account utente oppure da qualsiasi account nel computer.</span><span class="sxs-lookup"><span data-stu-id="71757-111">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="71757-112">Vedere l'enumerazione <xref:System.Security.Cryptography.DataProtectionScope> per una descrizione dettagliata delle opzioni di <xref:System.Security.Cryptography.ProtectedData>.</span><span class="sxs-lookup"><span data-stu-id="71757-112">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="71757-113">Per crittografare i dati in memoria mediante la protezione dei dati</span><span class="sxs-lookup"><span data-stu-id="71757-113">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="71757-114">Chiamare il metodo <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> statico durante il passaggio di una matrice di byte da crittografare, l'entropia e l'ambito di protezione della memoria.</span><span class="sxs-lookup"><span data-stu-id="71757-114">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="71757-115">Per decrittografare i dati in memoria mediante la protezione dei dati</span><span class="sxs-lookup"><span data-stu-id="71757-115">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="71757-116">Chiamare il metodo <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> statico durante il passaggio di una matrice di byte da decrittografare e l'ambito di protezione della memoria.</span><span class="sxs-lookup"><span data-stu-id="71757-116">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="71757-117">Per crittografare dati in un file o un flusso mediante la protezione dei dati</span><span class="sxs-lookup"><span data-stu-id="71757-117">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="71757-118">Creare l'entropia casuale.</span><span class="sxs-lookup"><span data-stu-id="71757-118">Create random entropy.</span></span>  
  
2. <span data-ttu-id="71757-119">Chiamare il metodo <xref:System.Security.Cryptography.ProtectedData.Protect%2A> statico durante il passaggio di una matrice di byte da crittografare, l'entropia e l'ambito di protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="71757-119">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="71757-120">Scrivere i dati crittografati in un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="71757-120">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="71757-121">Per decrittografare i dati da un file o un flusso mediante la protezione dati</span><span class="sxs-lookup"><span data-stu-id="71757-121">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="71757-122">Leggere i dati crittografati da un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="71757-122">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="71757-123">Chiamare il metodo <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> statico durante il passaggio di una matrice di byte da decrittografare e l'ambito di protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="71757-123">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71757-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="71757-124">Example</span></span>  
 <span data-ttu-id="71757-125">L'esempio di codice seguente mostra le due forme di crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="71757-125">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="71757-126">Prima di tutto, l'esempio di codice crittografa e quindi decrittografa una matrice in memoria di byte.</span><span class="sxs-lookup"><span data-stu-id="71757-126">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="71757-127">Quindi, l'esempio di codice crittografa una copia di una matrice di byte, la salva in un file, carica i dati di nuovo dal file e quindi li decrittografa.</span><span class="sxs-lookup"><span data-stu-id="71757-127">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="71757-128">L'esempio mostra i dati originali, i dati crittografati e i dati decrittografati.</span><span class="sxs-lookup"><span data-stu-id="71757-128">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71757-129">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="71757-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="71757-130">Includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="71757-130">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="71757-131">Includere gli spazi dei nomi <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> e <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="71757-131">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71757-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71757-132">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
