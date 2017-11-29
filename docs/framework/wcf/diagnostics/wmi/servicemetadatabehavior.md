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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d10fdd9e33b078fa392e0ef359372913f9ba133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="b6835-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b6835-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="b6835-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b6835-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6835-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6835-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="b6835-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6835-105">Methods</span></span>  
 <span data-ttu-id="b6835-106">La classe ServiceMetadataBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="b6835-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b6835-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b6835-107">Properties</span></span>  
 <span data-ttu-id="b6835-108">La classe ServiceMetadataBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6835-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="b6835-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="b6835-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="b6835-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b6835-110">Data type: string</span></span>  
  
 <span data-ttu-id="b6835-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b6835-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6835-112">Imposta il percorso a cui il servizio reindirizza richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="b6835-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="b6835-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b6835-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="b6835-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="b6835-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b6835-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b6835-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6835-116">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="b6835-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="b6835-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="b6835-117">HttpGetUrl</span></span>  
 <span data-ttu-id="b6835-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b6835-118">Data type: string</span></span>  
  
 <span data-ttu-id="b6835-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b6835-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6835-120">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6835-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="b6835-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b6835-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="b6835-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="b6835-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b6835-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b6835-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6835-124">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="b6835-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="b6835-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="b6835-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="b6835-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b6835-126">Data type: string</span></span>  
  
 <span data-ttu-id="b6835-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b6835-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6835-128">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6835-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6835-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6835-129">Requirements</span></span>  
  
|<span data-ttu-id="b6835-130">MOF</span><span class="sxs-lookup"><span data-stu-id="b6835-130">MOF</span></span>|<span data-ttu-id="b6835-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b6835-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b6835-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b6835-132">Namespace</span></span>|<span data-ttu-id="b6835-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6835-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6835-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6835-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
