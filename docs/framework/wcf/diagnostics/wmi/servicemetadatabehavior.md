---
title: ServiceMetadataBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c05f6be9fc0507b7e2f1de4374e3b9bbe3e2a10e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="ea6cf-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ea6cf-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="ea6cf-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ea6cf-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea6cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea6cf-104">Syntax</span></span>  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ea6cf-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ea6cf-105">Methods</span></span>  
 <span data-ttu-id="ea6cf-106">La classe ServiceMetadataBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ea6cf-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ea6cf-107">Properties</span></span>  
 <span data-ttu-id="ea6cf-108">La classe ServiceMetadataBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea6cf-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="ea6cf-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="ea6cf-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="ea6cf-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ea6cf-110">Data type: string</span></span>  
  
 <span data-ttu-id="ea6cf-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ea6cf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea6cf-112">Imposta il percorso a cui il servizio reindirizza richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="ea6cf-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ea6cf-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="ea6cf-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ea6cf-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ea6cf-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ea6cf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea6cf-116">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="ea6cf-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="ea6cf-117">HttpGetUrl</span></span>  
 <span data-ttu-id="ea6cf-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ea6cf-118">Data type: string</span></span>  
  
 <span data-ttu-id="ea6cf-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ea6cf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea6cf-120">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="ea6cf-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ea6cf-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="ea6cf-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ea6cf-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ea6cf-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ea6cf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea6cf-124">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="ea6cf-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="ea6cf-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="ea6cf-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ea6cf-126">Data type: string</span></span>  
  
 <span data-ttu-id="ea6cf-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ea6cf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea6cf-128">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea6cf-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea6cf-129">Requirements</span></span>  
  
|<span data-ttu-id="ea6cf-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ea6cf-130">MOF</span></span>|<span data-ttu-id="ea6cf-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ea6cf-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ea6cf-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ea6cf-132">Namespace</span></span>|<span data-ttu-id="ea6cf-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ea6cf-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea6cf-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea6cf-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
