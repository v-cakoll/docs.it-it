---
title: Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616853"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
In questa sezione vengono descritte le interfacce che gli host non gestiti possono utilizzare per integrare il Common Language Runtime (CLR) nel .NET Framework 4, .NET Framework 4,5 e versioni successive nelle applicazioni. Queste interfacce forniscono metodi che consentono a un host di configurare e caricare il runtime in un processo.  
  
 A partire da .NET Framework 4, tutte le interfacce di hosting presentano le seguenti caratteristiche:  
  
- Usano la gestione della durata ( `AddRef` e `Release` ), l'incapsulamento (contesto implicito) e `QueryInterface` da com.  
  
- Non usano tipi COM, ad esempio `BSTR` , `SAFEARRAY` o `VARIANT` .  
  
- Non sono disponibili modelli di Apartment, aggregazioni o attivazione del registro di sistema che utilizzano la [funzione CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)  
 Fornisce metodi che controllano l'utilizzo della CPU e della memoria del dominio dell'applicazione.  
  
 [Interfaccia ICLRDomainManager](iclrdomainmanager-interface.md)  
 Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.  
  
 [Interfaccia ICLRGCManager2](iclrgcmanager2-interface.md)  
 Fornisce il metodo [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) , che consente a un host di impostare le dimensioni del segmento Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection su valori maggiori di `DWORD` .  
  
 [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)  
 Fornisce metodi che restituiscono una versione specifica di CLR, elencano tutti i CLR installati, elencano tutti i runtime in-process, restituiscono l'interfaccia di attivazione e individuano la versione CLR utilizzata per compilare un assembly.  
  
 [Interfaccia ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)  
 Fornisce il metodo [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) che fornisce un'interfaccia CLR in base ai criteri, all'assembly gestito, alla versione e al file di configurazione.  
  
 [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)  
 Fornisce metodi che restituiscono informazioni su un runtime specifico, tra cui la versione, la directory e lo stato di caricamento.  
  
 [Interfaccia ICLRStrongName](iclrstrongname-interface.md)  
 Fornisce funzioni statiche globali di base per la firma di assembly con nomi sicuri. Tutti i metodi [ICLRStrongName](iclrstrongname-interface.md) restituiscono HRESULT COM standard.  
  
 [Interfaccia ICLRStrongName2](iclrstrongname2-interface.md)  
 Offre la possibilità di creare nomi sicuri usando il gruppo SHA-2 di algoritmi hash sicuri (SHA-256, SHA-384 e SHA-512).  
  
 [Interfaccia ICLRTask2](iclrtask2-interface.md)  
 Fornisce tutte le funzionalità dell' [interfaccia ICLRTask](iclrtask-interface.md); fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce di hosting CLR deprecate e coclassi](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Descrive le interfacce di hosting fornite con le versioni .NET Framework 1,0 e 1,1.  
  
 [Interfacce di hosting CLR](clr-hosting-interfaces.md)  
 Descrive le interfacce di hosting fornite con le versioni .NET Framework 2,0, 3,0 e 3,5.  
  
 [Hosting](index.md)  
 Introduce l'hosting nel .NET Framework.
