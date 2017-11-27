---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 36048f56c3b54447a112e6f0a457624062ce965a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
