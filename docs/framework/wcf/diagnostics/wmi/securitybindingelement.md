---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 601e3fafd9aa876186b7f78dfdcb87a2336ddfcd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185771"
---
# <a name="securitybindingelement"></a><span data-ttu-id="d8de5-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d8de5-102">SecurityBindingElement</span></span>
<span data-ttu-id="d8de5-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d8de5-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8de5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8de5-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d8de5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d8de5-105">Methods</span></span>  
 <span data-ttu-id="d8de5-106">La classe SecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d8de5-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d8de5-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d8de5-107">Properties</span></span>  
 <span data-ttu-id="d8de5-108">La classe SecurityBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8de5-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="d8de5-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d8de5-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="d8de5-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d8de5-110">Data type: string</span></span>  
  
 <span data-ttu-id="d8de5-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-112">Specifica gli algoritmi da usare con l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d8de5-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="d8de5-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="d8de5-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="d8de5-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="d8de5-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d8de5-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-116">Valore booleano che specifica se ogni messaggio contiene un timestamp.</span><span class="sxs-lookup"><span data-stu-id="d8de5-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="d8de5-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="d8de5-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="d8de5-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d8de5-118">Data type: string</span></span>  
  
 <span data-ttu-id="d8de5-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-120">Origine dell'entropia usata per creare chiavi.</span><span class="sxs-lookup"><span data-stu-id="d8de5-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="d8de5-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d8de5-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="d8de5-122">Tipo di dati: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d8de5-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="d8de5-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-124">Proprietà di sicurezza specifiche dell'associazione per il servizio locale.</span><span class="sxs-lookup"><span data-stu-id="d8de5-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="d8de5-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="d8de5-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="d8de5-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d8de5-126">Data type: string</span></span>  
  
 <span data-ttu-id="d8de5-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-128">Versione usata per la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d8de5-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="d8de5-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="d8de5-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="d8de5-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d8de5-130">Data type: string</span></span>  
  
 <span data-ttu-id="d8de5-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d8de5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8de5-132">Ordine degli elementi nell'intestazione di sicurezza di questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d8de5-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8de5-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8de5-133">Requirements</span></span>  
  
|<span data-ttu-id="d8de5-134">MOF</span><span class="sxs-lookup"><span data-stu-id="d8de5-134">MOF</span></span>|<span data-ttu-id="d8de5-135">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d8de5-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d8de5-136">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d8de5-136">Namespace</span></span>|<span data-ttu-id="d8de5-137">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d8de5-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8de5-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8de5-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
