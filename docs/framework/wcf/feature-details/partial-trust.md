---
title: Attendibilità parziale
ms.date: 03/30/2017
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
ms.openlocfilehash: f4eace87593f2b4c45101bafa0843998a093cbd5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579150"
---
# <a name="partial-trust"></a><span data-ttu-id="10b86-102">Attendibilità parziale</span><span class="sxs-lookup"><span data-stu-id="10b86-102">Partial Trust</span></span>

<span data-ttu-id="10b86-103">A partire da .NET Framework 3,5, i chiamanti parzialmente attendibili possono accedere ai tipi e ai metodi pubblici implementati in <xref:System.ServiceModel> , <xref:System.Runtime.Serialization> e <xref:System.ServiceModel.Web> .</span><span class="sxs-lookup"><span data-stu-id="10b86-103">Starting with the .NET Framework 3.5, partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="10b86-104">In questa sezione vengono descritti gli scenari supportati per l'utilizzo di Windows Communication Foundation (WCF) in un'applicazione parzialmente attendibile, nonché il subset limitato di funzionalità WCF disponibili per le applicazioni in esecuzione con autorizzazioni di sicurezza dall'accesso di codice ridotto.</span><span class="sxs-lookup"><span data-stu-id="10b86-104">This section describes supported scenarios for using Windows Communication Foundation (WCF) within a partially trusted application as well as the limited subset of WCF functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10b86-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="10b86-105">In This Section</span></span>  
 [<span data-ttu-id="10b86-106">Supported Deployment Scenarios</span><span class="sxs-lookup"><span data-stu-id="10b86-106">Supported Deployment Scenarios</span></span>](supported-deployment-scenarios.md)  
 <span data-ttu-id="10b86-107">Vengono descritti gli scenari di attendibilità parziale principali per l'esecuzione di WCF.</span><span class="sxs-lookup"><span data-stu-id="10b86-107">Describes the main partial trust scenarios for running WCF.</span></span>  
  
 [<span data-ttu-id="10b86-108">Compatibilità con la funzionalità di trust parziale</span><span class="sxs-lookup"><span data-stu-id="10b86-108">Partial Trust Feature Compatibility</span></span>](partial-trust-feature-compatibility.md)  
 <span data-ttu-id="10b86-109">Descrive le funzionalità WCF che non possono essere utilizzate con attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="10b86-109">Describes the WCF features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="10b86-110">T:System.Runtime.Serialization.DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="10b86-110">Partial Trust Best Practices</span></span>](partial-trust-best-practices.md)  
 <span data-ttu-id="10b86-111">Contiene le procedure consigliate per l'utilizzo di WCF in applicazioni parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="10b86-111">Contains best practices for using WCF in partially trusted applications.</span></span>
