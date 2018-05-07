---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Esegue il mapping di un servizio a un dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
