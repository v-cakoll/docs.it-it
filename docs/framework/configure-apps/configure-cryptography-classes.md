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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743251"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="afafc-102">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="afafc-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="afafc-103">Il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] consente agli amministratori di configurare gli algoritmi di crittografia predefinito e le implementazioni di algoritmi che usano .NET Framework e le applicazioni scritte in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="afafc-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="afafc-104">Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo di crittografia può utilizzare tale implementazione il valore predefinito anziché l'implementazione fornito con il [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afafc-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="afafc-105">Sebbene le applicazioni gestite che utilizzano la crittografia è comunque sempre possibile associare in modo esplicito a una particolare implementazione, è consigliabile creare oggetti di crittografia utilizzando il sistema di configurazione di crittografia.</span><span class="sxs-lookup"><span data-stu-id="afafc-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afafc-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="afafc-106">In This Section</span></span>  
 [<span data-ttu-id="afafc-107">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="afafc-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="afafc-108">Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="afafc-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="afafc-109">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="afafc-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="afafc-110">Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="afafc-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="afafc-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="afafc-111">Related Sections</span></span>  
 [<span data-ttu-id="afafc-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="afafc-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="afafc-113">Viene fornita una panoramica di servizi di crittografia forniti dal [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afafc-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="afafc-114">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="afafc-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="afafc-115">Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="afafc-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
