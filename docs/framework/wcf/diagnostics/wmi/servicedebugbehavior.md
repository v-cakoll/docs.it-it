---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af2dbd9e06876622b57379e17dbb4503cddbaac1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="83bb9-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="83bb9-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="83bb9-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="83bb9-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bb9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83bb9-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="83bb9-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="83bb9-105">Methods</span></span>  
 <span data-ttu-id="83bb9-106">La classe ServiceDebugBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="83bb9-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="83bb9-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="83bb9-107">Properties</span></span>  
 <span data-ttu-id="83bb9-108">La classe ServiceDebugBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="83bb9-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="83bb9-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="83bb9-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="83bb9-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="83bb9-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="83bb9-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="83bb9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83bb9-112">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="83bb9-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="83bb9-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="83bb9-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="83bb9-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="83bb9-114">Data type: string</span></span>  
  
 <span data-ttu-id="83bb9-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="83bb9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83bb9-116">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="83bb9-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="83bb9-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="83bb9-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="83bb9-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="83bb9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="83bb9-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="83bb9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83bb9-120">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="83bb9-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="83bb9-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="83bb9-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="83bb9-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="83bb9-122">Data type: string</span></span>  
  
 <span data-ttu-id="83bb9-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="83bb9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83bb9-124">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="83bb9-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="83bb9-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="83bb9-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="83bb9-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="83bb9-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="83bb9-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="83bb9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83bb9-128">Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="83bb9-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83bb9-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83bb9-129">Requirements</span></span>  
  
|<span data-ttu-id="83bb9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="83bb9-130">MOF</span></span>|<span data-ttu-id="83bb9-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="83bb9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="83bb9-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="83bb9-132">Namespace</span></span>|<span data-ttu-id="83bb9-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="83bb9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83bb9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83bb9-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
