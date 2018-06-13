---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: e96a732f8b3b4d78d597429905cc7dd290dcc606
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486000"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="6348d-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="6348d-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="6348d-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="6348d-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6348d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6348d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6348d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6348d-105">Methods</span></span>  
 <span data-ttu-id="6348d-106">La classe ServiceMetadataBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="6348d-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6348d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6348d-107">Properties</span></span>  
 <span data-ttu-id="6348d-108">La classe ServiceMetadataBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="6348d-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="6348d-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="6348d-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="6348d-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="6348d-110">Data type: string</span></span>  
  
 <span data-ttu-id="6348d-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6348d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6348d-112">Imposta il percorso a cui il servizio reindirizza richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="6348d-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="6348d-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="6348d-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="6348d-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="6348d-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="6348d-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6348d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6348d-116">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="6348d-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="6348d-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="6348d-117">HttpGetUrl</span></span>  
 <span data-ttu-id="6348d-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="6348d-118">Data type: string</span></span>  
  
 <span data-ttu-id="6348d-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6348d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6348d-120">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="6348d-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="6348d-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="6348d-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="6348d-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="6348d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="6348d-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6348d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6348d-124">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="6348d-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="6348d-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="6348d-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="6348d-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="6348d-126">Data type: string</span></span>  
  
 <span data-ttu-id="6348d-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="6348d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6348d-128">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6348d-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6348d-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6348d-129">Requirements</span></span>  
  
|<span data-ttu-id="6348d-130">MOF</span><span class="sxs-lookup"><span data-stu-id="6348d-130">MOF</span></span>|<span data-ttu-id="6348d-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6348d-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6348d-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="6348d-132">Namespace</span></span>|<span data-ttu-id="6348d-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6348d-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6348d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6348d-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
