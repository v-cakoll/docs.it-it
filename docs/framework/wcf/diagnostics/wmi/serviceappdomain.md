---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192239"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Esegue il mapping di un servizio a un dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceAppDomain non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceAppDomain presenta le proprietà seguenti:  
  
### <a name="ref"></a>ref  
 Tipo di dati: servizio  
Qualificatori: chiave  
  
 Tipo di accesso: sola lettura  
  
 Il servizio di questo dominio applicazione.  
  
### <a name="ref"></a>ref  
 Tipo di dati: AppDomainInfo  
Qualificatori: chiave  
  
 Tipo di accesso: sola lettura  
  
 Contiene proprietà del dominio applicazione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
