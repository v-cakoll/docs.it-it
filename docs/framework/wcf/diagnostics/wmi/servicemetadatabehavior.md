---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976137"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="c4187-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="c4187-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="c4187-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="c4187-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4187-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4187-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c4187-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c4187-105">Methods</span></span>  
 <span data-ttu-id="c4187-106">La classe ServiceMetadataBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c4187-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c4187-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c4187-107">Properties</span></span>  
 <span data-ttu-id="c4187-108">La classe ServiceMetadataBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4187-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="c4187-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="c4187-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="c4187-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4187-110">Data type: string</span></span>  
  
 <span data-ttu-id="c4187-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4187-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4187-112">Imposta il percorso a cui il servizio reindirizza richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="c4187-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="c4187-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="c4187-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="c4187-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4187-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4187-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4187-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4187-116">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="c4187-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="c4187-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="c4187-117">HttpGetUrl</span></span>  
 <span data-ttu-id="c4187-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4187-118">Data type: string</span></span>  
  
 <span data-ttu-id="c4187-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4187-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4187-120">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4187-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="c4187-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="c4187-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="c4187-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4187-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4187-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4187-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4187-124">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="c4187-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="c4187-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="c4187-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="c4187-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4187-126">Data type: string</span></span>  
  
 <span data-ttu-id="c4187-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4187-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4187-128">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c4187-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4187-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4187-129">Requirements</span></span>  
  
|<span data-ttu-id="c4187-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c4187-130">MOF</span></span>|<span data-ttu-id="c4187-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c4187-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c4187-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c4187-132">Namespace</span></span>|<span data-ttu-id="c4187-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c4187-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4187-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4187-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
