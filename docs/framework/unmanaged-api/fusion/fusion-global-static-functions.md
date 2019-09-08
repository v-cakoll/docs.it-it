---
title: Funzioni statiche globali Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a8f15bc862c0486311960f7567c49424859846e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795324"
---
# <a name="fusion-global-static-functions"></a>Funzioni statiche globali Fusion
Questa sezione descrive le funzioni statiche globali non gestite utilizzate dall'API Fusion.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione ClearDownloadCache](cleardownloadcache-function.md)  
 Cancella il Global Assembly Cache degli assembly scaricati.  
  
 [Funzione CompareAssemblyIdentity](compareassemblyidentity-function.md)  
 Confronta due identità di assembly per determinare se sono equivalenti.  
  
 [Funzione CreateApplicationContext](createapplicationcontext-function.md)  
 Solo interno. Questa funzione supporta l'infrastruttura .NET Framework e non può essere utilizzata direttamente dal codice.  
  
 [Funzione CreateAssemblyCache](createassemblycache-function.md)  
 Ottiene un puntatore a una nuova istanza di [IAssemblyCache](iassemblycache-interface.md) che rappresenta l'global assembly cache.  
  
 [Funzione CreateAssemblyEnum](createassemblyenum-function.md)  
 Ottiene un puntatore a un'istanza di [IAssemblyEnum](iassemblyenum-interface.md) che rappresenta un elenco di oggetti presenti nell'assembly specificato.  
  
 [Funzione CreateAssemblyNameObject](createassemblynameobject-function.md)  
 Ottiene un puntatore a un'istanza di [IAssemblyName](iassemblyname-interface.md) che rappresenta l'identità univoca dell'assembly con il nome specificato.  
  
 [Funzione CreateHistoryReader](createhistoryreader-function.md)  
 Crea un lettore della cronologia per il file specificato.  
  
 [Funzione CreateInstallReferenceEnum](createinstallreferenceenum-function.md)  
 Ottiene un puntatore a un'istanza di [IInstallReferenceEnum](iinstallreferenceenum-interface.md) che rappresenta un elenco di riferimenti di un'applicazione all'assembly specificato.  
  
 [Funzione GetAppIdAuthority](getappidauthority-function.md)  
 Ottiene un puntatore a un'istanza di [IAppIdAuthority](iappidauthority-interface.md) che gestisce le chiavi per le identità dell'applicazione e i riferimenti.  
  
 [Funzione GetAssemblyIdentityFromFile](getassemblyidentityfromfile-function.md)  
 Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto `IID` specificato nell'assembly nel percorso del file specificato.  
  
 [Funzione GetCachePath](getcachepath-function.md)  
 Ottiene il percorso dell'assembly memorizzato nella cache, usando i flag specificati.  
  
 [Funzione GetHistoryFileDirectory](gethistoryfiledirectory-function.md)  
 Recupera il percorso della directory della cronologia dell'applicazione.  
  
 [Funzione GetIdentityAuthority](getidentityauthority-function.md)  
 Ottiene un puntatore a un'istanza di [IIdentityAuthority](iidentityauthority-interface.md) che gestisce le chiavi per gli oggetti di codice.  
  
 [Funzione IsFrameworkAssembly](isframeworkassembly-function.md)  
 Ottiene un valore che indica se l'assembly specificato è gestito.  
  
 [Funzione NukeDownloadedCache](nukedownloadedcache-function.md)  
 Elimina la Common Language Runtime Download Cache.  
  
 [Funzione PreBindAssemblyEx](prebindassemblyex-function.md)  
 Ottiene il nome visualizzato post-criteri per un assembly.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce Fusion](fusion-interfaces.md)  
  
 [Enumerazioni Fusion](fusion-enumerations.md)  
  
 [Strutture Fusion](fusion-structures.md)  
  
 [Global Assembly Cache](../../app-domains/gac.md)
