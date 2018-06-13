---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: aa852ff82c44a3b5009dbc70e1067face44cbbe9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486376"
---
# <a name="clientcredentials"></a><span data-ttu-id="37ab3-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="37ab3-102">ClientCredentials</span></span>
<span data-ttu-id="37ab3-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="37ab3-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ab3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37ab3-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="37ab3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="37ab3-105">Methods</span></span>  
 <span data-ttu-id="37ab3-106">La classe ClientCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="37ab3-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="37ab3-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37ab3-107">Properties</span></span>  
 <span data-ttu-id="37ab3-108">La classe ClientCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="37ab3-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="37ab3-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="37ab3-109">ClientCertificate</span></span>  
 <span data-ttu-id="37ab3-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-110">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-112">Certificato X.509 utilizzato dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="37ab3-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="37ab3-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="37ab3-113">HttpDigest</span></span>  
 <span data-ttu-id="37ab3-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-114">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-116">Credenziale digest HTTP corrente.</span><span class="sxs-lookup"><span data-stu-id="37ab3-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="37ab3-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="37ab3-117">IssuedToken</span></span>  
 <span data-ttu-id="37ab3-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-118">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-120">Indirizzo e associazione dell'endpoint utilizzati per contattare il servizio locale del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="37ab3-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="37ab3-121">Peer</span><span class="sxs-lookup"><span data-stu-id="37ab3-121">Peer</span></span>  
 <span data-ttu-id="37ab3-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-122">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-124">Credenziali utilizzate dal nodo peer per l'autenticazione con gli altri nodi nella rete.</span><span class="sxs-lookup"><span data-stu-id="37ab3-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="37ab3-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="37ab3-125">ServiceCertificate</span></span>  
 <span data-ttu-id="37ab3-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-126">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-128">Certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="37ab3-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="37ab3-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="37ab3-129">SupportInteractive</span></span>  
 <span data-ttu-id="37ab3-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="37ab3-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="37ab3-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-132">Valore booleano che specifica se la credenziale supporta negoziazioni interattive.</span><span class="sxs-lookup"><span data-stu-id="37ab3-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="37ab3-133">UserName</span><span class="sxs-lookup"><span data-stu-id="37ab3-133">UserName</span></span>  
 <span data-ttu-id="37ab3-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-134">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-136">Nome utente e password utilizzati dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="37ab3-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="37ab3-137">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="37ab3-137">Windows</span></span>  
 <span data-ttu-id="37ab3-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37ab3-138">Data type: string</span></span>  
  
 <span data-ttu-id="37ab3-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="37ab3-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37ab3-140">Credenziali Windows utilizzate dal client per l'autenticazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="37ab3-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ab3-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37ab3-141">Requirements</span></span>  
  
|<span data-ttu-id="37ab3-142">MOF</span><span class="sxs-lookup"><span data-stu-id="37ab3-142">MOF</span></span>|<span data-ttu-id="37ab3-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="37ab3-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="37ab3-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="37ab3-144">Namespace</span></span>|<span data-ttu-id="37ab3-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37ab3-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37ab3-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37ab3-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>
