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
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927777"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="f2949-102">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f2949-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="f2949-103">Il Windows SDK consente agli amministratori di computer di configurare gli algoritmi di crittografia e le implementazioni degli algoritmi predefiniti che vengono utilizzati dall'.NET Framework e dalle applicazioni scritte in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f2949-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="f2949-104">Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo crittografico può rendere tale implementazione il valore predefinito anziché l'implementazione fornita nel Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f2949-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="f2949-105">Sebbene le applicazioni gestite che usano la crittografia possano sempre scegliere di eseguire un'associazione esplicita a una particolare implementazione, è consigliabile creare oggetti crittografici usando il sistema di configurazione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="f2949-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2949-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f2949-106">In This Section</span></span>  
 [<span data-ttu-id="f2949-107">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f2949-107">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="f2949-108">Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f2949-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="f2949-109">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f2949-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="f2949-110">Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f2949-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f2949-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f2949-111">Related Sections</span></span>  
 [<span data-ttu-id="f2949-112">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f2949-112">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="f2949-113">Viene fornita una panoramica dei servizi di crittografia forniti dal Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f2949-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="f2949-114">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="f2949-114">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="f2949-115">Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f2949-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
