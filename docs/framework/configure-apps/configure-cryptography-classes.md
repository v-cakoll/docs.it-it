---
title: Configurazione di classi di crittografia
description: Informazioni su come gli amministratori di computer possono configurare gli algoritmi di crittografia e le implementazioni di algoritmi predefiniti usati da .NET e dalle applicazioni.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5d12aae31ec78f80bea7df1bb0f37ac78dc37de2
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105072"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="351d7-103">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="351d7-103">Configuring Cryptography Classes</span></span>
<span data-ttu-id="351d7-104">Il Windows SDK consente agli amministratori di computer di configurare gli algoritmi di crittografia e le implementazioni degli algoritmi predefiniti che vengono utilizzati dall'.NET Framework e dalle applicazioni scritte in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="351d7-104">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="351d7-105">Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo crittografico può rendere tale implementazione il valore predefinito anziché l'implementazione fornita nel Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="351d7-105">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="351d7-106">Sebbene le applicazioni gestite che usano la crittografia possano sempre scegliere di eseguire un'associazione esplicita a una particolare implementazione, è consigliabile creare oggetti crittografici usando il sistema di configurazione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="351d7-106">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="351d7-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="351d7-107">In This Section</span></span>  
 [<span data-ttu-id="351d7-108">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="351d7-108">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="351d7-109">Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="351d7-109">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="351d7-110">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="351d7-110">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="351d7-111">Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="351d7-111">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="351d7-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="351d7-112">Related Sections</span></span>  
 [<span data-ttu-id="351d7-113">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="351d7-113">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="351d7-114">Viene fornita una panoramica dei servizi di crittografia forniti dal Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="351d7-114">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="351d7-115">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="351d7-115">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="351d7-116">Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="351d7-116">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
