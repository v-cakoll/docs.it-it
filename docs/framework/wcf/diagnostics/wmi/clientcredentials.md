---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771205"
---
# <a name="clientcredentials"></a><span data-ttu-id="04fc6-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="04fc6-102">ClientCredentials</span></span>
<span data-ttu-id="04fc6-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="04fc6-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04fc6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04fc6-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="04fc6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="04fc6-105">Methods</span></span>  
 <span data-ttu-id="04fc6-106">La classe ClientCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="04fc6-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="04fc6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="04fc6-107">Properties</span></span>  
 <span data-ttu-id="04fc6-108">La classe ClientCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="04fc6-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="04fc6-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="04fc6-109">ClientCertificate</span></span>  
 <span data-ttu-id="04fc6-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-110">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-112">Certificato X.509 utilizzato dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="04fc6-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="04fc6-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="04fc6-113">HttpDigest</span></span>  
 <span data-ttu-id="04fc6-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-114">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-116">Credenziale digest HTTP corrente.</span><span class="sxs-lookup"><span data-stu-id="04fc6-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="04fc6-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="04fc6-117">IssuedToken</span></span>  
 <span data-ttu-id="04fc6-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-118">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-120">Indirizzo e associazione dell'endpoint utilizzati per contattare il servizio locale del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="04fc6-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="04fc6-121">Peer</span><span class="sxs-lookup"><span data-stu-id="04fc6-121">Peer</span></span>  
 <span data-ttu-id="04fc6-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-122">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-124">Credenziali utilizzate dal nodo peer per l'autenticazione con gli altri nodi nella rete.</span><span class="sxs-lookup"><span data-stu-id="04fc6-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="04fc6-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="04fc6-125">ServiceCertificate</span></span>  
 <span data-ttu-id="04fc6-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-126">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-128">Certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="04fc6-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="04fc6-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="04fc6-129">SupportInteractive</span></span>  
 <span data-ttu-id="04fc6-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="04fc6-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="04fc6-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-132">Valore booleano che specifica se la credenziale supporta negoziazioni interattive.</span><span class="sxs-lookup"><span data-stu-id="04fc6-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="04fc6-133">UserName</span><span class="sxs-lookup"><span data-stu-id="04fc6-133">UserName</span></span>  
 <span data-ttu-id="04fc6-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-134">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-136">Nome utente e password utilizzati dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="04fc6-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="04fc6-137">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="04fc6-137">Windows</span></span>  
 <span data-ttu-id="04fc6-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="04fc6-138">Data type: string</span></span>  
  
 <span data-ttu-id="04fc6-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="04fc6-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04fc6-140">Credenziali Windows utilizzate dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="04fc6-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04fc6-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04fc6-141">Requirements</span></span>  
  
|<span data-ttu-id="04fc6-142">MOF</span><span class="sxs-lookup"><span data-stu-id="04fc6-142">MOF</span></span>|<span data-ttu-id="04fc6-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="04fc6-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="04fc6-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="04fc6-144">Namespace</span></span>|<span data-ttu-id="04fc6-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="04fc6-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04fc6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04fc6-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
