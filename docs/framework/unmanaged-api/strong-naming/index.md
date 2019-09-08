---
title: Denominazione sicura (riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a697d96864f336982c05b5bcc7c48efef2df0f6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799208"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="d554d-102">Denominazione sicura (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d554d-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="d554d-103">L'API di denominazione sicura consente a un client di amministrare la firma con nome sicuro per gli assembly.</span><span class="sxs-lookup"><span data-stu-id="d554d-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="d554d-104">La firma di un assembly con un nome sicuro comporta l'aggiunta di una crittografia con chiave pubblica al file che contiene il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d554d-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="d554d-105">La firma con nome sicuro garantisce l'univocità del nome, ne impedisce l'utilizzo fraudolento e fornisce un'identità univoca al chiamante quando viene risolto un riferimento.</span><span class="sxs-lookup"><span data-stu-id="d554d-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="d554d-106">I nomi sicuri non garantiscono tuttavia nessun grado di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="d554d-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d554d-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d554d-107">In This Section</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d554d-108">Tutte queste funzioni sono state deprecate a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-108">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="d554d-109">Per le proposte alternative, vedere l'interfaccia [ICLRStrongName](../hosting/iclrstrongname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d554d-109">For suggested alternatives, see the [ICLRStrongName](../hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="d554d-110">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d554d-110">GetHashFromAssemblyFile Function</span></span>](gethashfromassemblyfile-function.md)  
 <span data-ttu-id="d554d-111">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="d554d-112">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-113">Funzione GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="d554d-113">GetHashFromAssemblyFileW Function</span></span>](gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="d554d-114">Ottiene un hash del file di assembly specificato come stringa Unicode usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="d554d-115">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-116">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d554d-116">GetHashFromBlob Function</span></span>](gethashfromblob-function.md)  
 <span data-ttu-id="d554d-117">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="d554d-118">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-119">Funzione GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="d554d-119">GetHashFromFile Function</span></span>](gethashfromfile-function.md)  
 <span data-ttu-id="d554d-120">Genera un hash basato sul contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="d554d-121">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-122">Funzione GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="d554d-122">GetHashFromFileW Function</span></span>](gethashfromfilew-function.md)  
 <span data-ttu-id="d554d-123">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="d554d-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="d554d-124">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-125">Funzione GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="d554d-125">GetHashFromHandle Function</span></span>](gethashfromhandle-function.md)  
 <span data-ttu-id="d554d-126">Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="d554d-127">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-128">Funzione StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="d554d-128">StrongNameCompareAssemblies Function</span></span>](strongnamecompareassemblies-function.md)  
 <span data-ttu-id="d554d-129">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="d554d-130">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-131">Funzione StrongNameErrorInfo</span><span class="sxs-lookup"><span data-stu-id="d554d-131">StrongNameErrorInfo Function</span></span>](strongnameerrorinfo-function.md)  
 <span data-ttu-id="d554d-132">Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="d554d-133">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d554d-133">StrongNameFreeBuffer Function</span></span>](strongnamefreebuffer-function.md)  
 <span data-ttu-id="d554d-134">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="d554d-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="d554d-135">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-136">Funzione StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="d554d-136">StrongNameGetBlob Function</span></span>](strongnamegetblob-function.md)  
 <span data-ttu-id="d554d-137">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="d554d-138">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-139">Funzione StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="d554d-139">StrongNameGetBlobFromImage Function</span></span>](strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="d554d-140">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="d554d-141">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-142">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="d554d-142">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)  
 <span data-ttu-id="d554d-143">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="d554d-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="d554d-144">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-145">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="d554d-145">StrongNameHashSize Function</span></span>](strongnamehashsize-function.md)  
 <span data-ttu-id="d554d-146">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="d554d-147">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-148">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="d554d-148">StrongNameKeyDelete Function</span></span>](strongnamekeydelete-function.md)  
 <span data-ttu-id="d554d-149">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-149">Deletes the specified key container.</span></span> <span data-ttu-id="d554d-150">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-151">Funzione StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="d554d-151">StrongNameKeyGen Function</span></span>](strongnamekeygen-function.md)  
 <span data-ttu-id="d554d-152">Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="d554d-153">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-154">Funzione StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="d554d-154">StrongNameKeyGenEx Function</span></span>](strongnamekeygenex-function.md)  
 <span data-ttu-id="d554d-155">Genera una nuova coppia di chiavi pubblica/privata con le dimensioni chiave specificate per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="d554d-156">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-157">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="d554d-157">StrongNameKeyInstall Function</span></span>](strongnamekeyinstall-function.md)  
 <span data-ttu-id="d554d-158">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="d554d-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="d554d-159">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-160">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="d554d-160">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="d554d-161">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="d554d-162">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-163">Funzione StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="d554d-163">StrongNameSignatureGenerationEx Function</span></span>](strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="d554d-164">Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="d554d-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="d554d-165">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-166">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="d554d-166">StrongNameSignatureSize Function</span></span>](strongnamesignaturesize-function.md)  
 <span data-ttu-id="d554d-167">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="d554d-168">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-169">Funzione StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="d554d-169">StrongNameSignatureVerification Function</span></span>](strongnamesignatureverification-function.md)  
 <span data-ttu-id="d554d-170">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="d554d-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="d554d-171">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-172">Funzione StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="d554d-172">StrongNameSignatureVerificationEx Function</span></span>](strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="d554d-173">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d554d-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="d554d-174">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-175">Funzione StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="d554d-175">StrongNameSignatureVerificationFromImage Function</span></span>](strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="d554d-176">Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.</span><span class="sxs-lookup"><span data-stu-id="d554d-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="d554d-177">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-178">Funzione StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="d554d-178">StrongNameTokenFromAssembly Function</span></span>](strongnametokenfromassembly-function.md)  
 <span data-ttu-id="d554d-179">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="d554d-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="d554d-180">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-181">Funzione StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="d554d-181">StrongNameTokenFromAssemblyEx Function</span></span>](strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="d554d-182">Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d554d-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="d554d-183">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-184">Funzione StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="d554d-184">StrongNameTokenFromPublicKey Function</span></span>](strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="d554d-185">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d554d-185">Gets a token representing a public key.</span></span> <span data-ttu-id="d554d-186">Deprecata a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d554d-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d554d-187">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="d554d-187">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)  
 <span data-ttu-id="d554d-188">Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata in formato binario.</span><span class="sxs-lookup"><span data-stu-id="d554d-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d554d-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d554d-189">See also</span></span>

- [<span data-ttu-id="d554d-190">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d554d-190">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="d554d-191">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="d554d-191">Unmanaged API Reference</span></span>](../index.md)
