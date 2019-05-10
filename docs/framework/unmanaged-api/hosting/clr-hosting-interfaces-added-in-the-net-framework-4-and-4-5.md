---
title: Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96bc833915dd74756220b5e79a2866b41389dd45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630500"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
In questa sezione vengono descritte le interfacce che non gestiti gli host possono usare per l'integrazione common language runtime (CLR) nei [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]e versioni successive nelle proprie applicazioni. Queste interfacce forniscono metodi per un host configurare e caricare il runtime in un processo.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], hosting di tutte le interfacce hanno le caratteristiche seguenti:  
  
- Usano la gestione della durata (`AddRef` e `Release`), incapsulamento (contesto implicito) e `QueryInterface` da COM.  
  
- Non utilizzano i tipi COM, ad esempio `BSTR`, `SAFEARRAY`, o `VARIANT`.  
  
- Non sono presenti modelli di apartment, aggregazione o l'attivazione del Registro di sistema che usano il [funzione CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Fornisce metodi per controllare memoria e utilizzo della CPU di un dominio dell'applicazione.  
  
 [Interfaccia ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Consente all'host specificare il gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito e specificare le proprietà di inizializzazione.  
  
 [Interfaccia ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Fornisce il [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) metodo, che consente a un host impostare le dimensioni del segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori maggiore `DWORD`.  
  
 [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Fornisce metodi che restituiscono una versione specifica di CLR, elencano tutti i runtime installati, elencare tutti i runtime in-process, restituiscono l'interfaccia di attivazione e individuano la versione CLR usata per compilare un assembly.  
  
 [Interfaccia ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo che fornisce un'interfaccia CLR in base ai criteri, assembly gestito, versione e file di configurazione.  
  
 [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Fornisce metodi che restituiscono informazioni su una specifica del runtime, inclusi lo stato di caricamento, directory e versione.  
  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Fornisce funzioni statiche globali di base per la firma degli assembly con nomi sicuri. Tutti i [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) metodi restituiscono valori HRESULT COM standard.  
  
 [Interfaccia ICLRStrongName2](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Offre la possibilità di creare i nomi sicuri usando il gruppo di SHA-2 di algoritmi Secure Hash (SHA-256, SHA-384 e SHA-512).  
  
 [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Fornisce tutte le funzionalità dei [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); inoltre, fornisce metodi che consentono le interruzioni dei thread per essere ritardato sul thread corrente.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce di hosting CLR deprecate e coclassi](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Descrive le interfacce di hosting fornite con le versioni di .NET Framework 1.0 e 1.1.  
  
 [Interfacce di hosting CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Descrive le interfacce di hosting fornite con le versioni di .NET Framework 2.0, 3.0 e 3.5.  
  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Viene introdotto l'hosting di .NET Framework.
