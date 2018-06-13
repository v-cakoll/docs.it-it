---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bf906e09ae71d26f8e95877f1c545c0724d57b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485756"
---
# <a name="servicecredentials"></a><span data-ttu-id="4b593-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4b593-102">ServiceCredentials</span></span>
<span data-ttu-id="4b593-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4b593-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b593-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b593-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b593-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4b593-105">Methods</span></span>  
 <span data-ttu-id="4b593-106">La classe ServiceCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4b593-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b593-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b593-107">Properties</span></span>  
 <span data-ttu-id="4b593-108">La classe ServiceCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b593-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="4b593-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4b593-109">ClientCertificate</span></span>  
 <span data-ttu-id="4b593-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-110">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-112">Impostazioni di provisioning e autenticazione dei certificati client per il servizio.</span><span class="sxs-lookup"><span data-stu-id="4b593-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="4b593-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b593-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="4b593-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-114">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-116">Impostazioni correnti di autenticazione del token rilasciato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="4b593-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="4b593-117">Peer</span><span class="sxs-lookup"><span data-stu-id="4b593-117">Peer</span></span>  
 <span data-ttu-id="4b593-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-118">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-120">Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.</span><span class="sxs-lookup"><span data-stu-id="4b593-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="4b593-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b593-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="4b593-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-122">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-124">Specifica le impostazioni correnti per le conversazioni protette.</span><span class="sxs-lookup"><span data-stu-id="4b593-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="4b593-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="4b593-125">ServiceCertificate</span></span>  
 <span data-ttu-id="4b593-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-126">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-128">Certificato associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="4b593-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="4b593-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b593-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="4b593-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-130">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-132">Impostazioni di nome utente e password per il servizio.</span><span class="sxs-lookup"><span data-stu-id="4b593-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="4b593-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b593-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="4b593-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4b593-134">Data type: string</span></span>  
  
 <span data-ttu-id="4b593-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b593-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b593-136">Impostazioni di autenticazione Windows per il servizio.</span><span class="sxs-lookup"><span data-stu-id="4b593-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b593-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b593-137">Requirements</span></span>  
  
|<span data-ttu-id="4b593-138">MOF</span><span class="sxs-lookup"><span data-stu-id="4b593-138">MOF</span></span>|<span data-ttu-id="4b593-139">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4b593-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b593-140">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4b593-140">Namespace</span></span>|<span data-ttu-id="4b593-141">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b593-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b593-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b593-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
