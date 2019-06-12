---
title: Configurazione di classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 23bf831a4374add55258f5fb41c17a5d4a8f14c3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832807"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="fcdb6-102">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="fcdb6-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="fcdb6-103">Windows Software Development Kit (SDK) consente agli amministratori di computer configurare gli algoritmi di crittografia predefinito e implementazioni di algoritmi che usano .NET Framework e le applicazioni scritte in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-103">The Windows Software Development Kit (SDK) allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="fcdb6-104">Ad esempio, un'azienda che ha la propria implementazione di un algoritmo di crittografia può utilizzare tale implementazione il valore predefinito anziché l'implementazione fornito nel SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="fcdb6-105">Sebbene le applicazioni gestite che usano crittografia sempre possono scegliere di associare in modo esplicito a una particolare implementazione, è consigliabile che creano oggetti di crittografia utilizzando il sistema di configurazione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcdb6-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fcdb6-106">In This Section</span></span>  
 [<span data-ttu-id="fcdb6-107">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="fcdb6-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="fcdb6-108">Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="fcdb6-109">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="fcdb6-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="fcdb6-110">Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fcdb6-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fcdb6-111">Related Sections</span></span>  
 [<span data-ttu-id="fcdb6-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="fcdb6-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="fcdb6-113">Fornisce una panoramica di servizi di crittografia forniti da Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="fcdb6-114">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="fcdb6-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="fcdb6-115">Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="fcdb6-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
