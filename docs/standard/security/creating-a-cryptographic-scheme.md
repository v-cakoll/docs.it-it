---
title: Creazione di uno schema di crittografia
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2db6d4229ac777801aff792c86fe0e5e9a1b4994
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44031695"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="cfe7e-102">Creazione di uno schema di crittografia</span><span class="sxs-lookup"><span data-stu-id="cfe7e-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="cfe7e-103">I componenti di crittografia di .NET Framework possono essere combinati per creare diversi schemi per la crittografia e la decrittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="cfe7e-104">Uno schema di crittografia semplice per la crittografia e la decrittografia dei dati può specificare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfe7e-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="cfe7e-105">Ogni parte genera una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="cfe7e-106">Le parti si scambiano le chiavi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="cfe7e-107">Ogni parte genera una chiave segreta per la crittografia TripleDES, ad esempio, e crittografa la nuova chiave creata usando la chiave pubblica dell'altra parte.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="cfe7e-108">Ogni parte invia i dati all'altra parte e combina la chiave segreta dell'altra parte con la propria, in un ordine specifico, per creare una nuova chiave segreta.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="cfe7e-109">Le parti avviano quindi una conversazione usando la crittografia simmetrica.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="cfe7e-110">La creazione di uno schema di crittografia non è un'attività banale.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="cfe7e-111">Per altre informazioni sull'uso della crittografia, vedere l'argomento crittografia nella documentazione di Platform SDK al http://msdn.microsoft.com/library.</span><span class="sxs-lookup"><span data-stu-id="cfe7e-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe7e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfe7e-112">See also</span></span>

- [<span data-ttu-id="cfe7e-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="cfe7e-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
