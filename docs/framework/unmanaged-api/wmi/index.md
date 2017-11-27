---
title: WMI e i contatori delle prestazioni (riferimenti alle API non gestite)
description: Vengono riepilogate in .NET Framework API non gestita per informazioni sui contatori di prestazioni e WMI.
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.date: 11/06/2017
ms.topic: article-type-from-white-list
ms.prod: .net-framework
ms.devlang: cpp
ms.openlocfilehash: 461d90aaf5beca1c0f1d1965ce0ea07411e56e79
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Strumentazione gestione Windows (WMI) e i contatori delle prestazioni (riferimenti alle API non gestite)

L'API non gestita di .NET Framework WMI e i contatori delle prestazioni è costituito da un set di funzioni che eseguono il wrapping di chiamate per il [API di Strumentazione gestione Windows nativo](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx). Consente di sviluppare strumenti e librerie di gestire e monitorare i sistemi di computer remoto.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
L'API include le funzioni seguenti:

| Funzione | Descrizione |
|---------|---------|
| [BeginEnumeration (funzione)](beginenumeration.md) | Reimposta l'enumeratore all'inizio di un'enumerazione di proprietà dell'oggetto WMI. |
| [BeginMethodEnumeration (funzione)](beginmethodenumeration.md) |  Avvia un'enumerazione dei metodi disponibili per un oggetto. |
| [BlessIWbemServices (funzione)](blessiwbemservices.md) | Indica se le credenziali utente di consentono l'accesso a una classe IWbemServices specificata. |
| [BlessIWbemServicesObject (funzione)](blessiwbemservicesobject.md) | Indica se le credenziali utente di consentono l'accesso a un oggetto servizio IWbem specificato. |
| [Clone (funzione)](clone.md) | Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente. |
| [CloneEnumWbemClassObject (funzione)](cloneenumwbemclassobject.md) | Crea una copia logica di un enumeratore, mantenendo la posizione corrente nell'enumerazione. |
| [CompareTo (funzione)](compareto.md) | Confronta un oggetto a un altro oggetto di gestione di Windows. |
| [ConnectServerWmi (funzione)](connectserverwmi.md) | Crea una connessione mediante DCOM uno spazio dei nomi WMI in un computer specifico. |
| [CreateClassEnumWmi (funzione)](createclassenumwmi.md) | Restituisce un enumeratore per tutte le classi che soddisfano i criteri di selezione specificati. |
| [CreateInstanceEnumWmi (funzione)](createinstanceenumwmi.md) | Restituisce un enumeratore che restituisce le istanze di una classe specificata che soddisfano i criteri di selezione specificati. |
| [Eliminare la funzione](delete.md) | Elimina una proprietà specificata da una definizione di classe e tutti i relativi qualificatori. |
| [Funzione DeleteMethod](deletemethod.md) | Elimina un metodo specificato da una definizione di classe CIM. |
| [EndEnumeration (funzione)](endenumeration.md) | Termina una sequenza di enumerazione. | 
| [EndMethodEnumeration (funzione)](endmethodenumeration.md) | Termina una sequenza di enumerazione avviata chiamando il [BeginMethodEnumeration funzione](beginmethodenumeration.md). |
| [ExecNotificationQueryWmi (funzione)](execnotificationquerywmi.md) | Esegue una query per la ricezione di eventi. |
| [ExecQueryWmi (funzione)](execquerywmi.md) | Esegue una query per recuperare gli oggetti. |
| [FormatFromRawValue (funzione)](formatfromrawvalue.md) | Converte un valore di dati delle prestazioni non elaborati nel formato specificato o due valori di tali dati se la conversione di formato è basato sul tempo. | 
| [Get (funzione)](get.md) | Recupera un valore della proprietà specificata, se esistente. |
| [GetCurrentApartmentType (funzione)](getcurrentapartmenttype.md) | Recupera il tipo di apartment, in cui il chiamante è in esecuzione. |
| [GetDemultiplexedStub (funzione)](getdemultiplexedstub.md) | Crea un oggetto sink di server d'inoltro per facilitare un client riceve le chiamate asincrone dalla gestione di Windows. |
| [GetErrorInfo (funzione)](geterrorinfo.md) | Recupera informazioni sull'errore nella chiamata alla funzione precedente. | 
| [GetMethod (funzione)](getmethod.md) | Recupera le informazioni relative al metodo specificato. | 
| [GetMethodOrigin (funzione)](getmethodorigin.md) | Determina la classe in cui viene dichiarato un metodo. |
| [GetMethodQualifierSet (funzione)](getmethodqualifierset.md) | Recupera il qualificatore impostato per un metodo specifico. |
| [GetNames (funzione)](getnames.md) | Recupera un subset o tutti i nomi delle proprietà di un oggetto. |
| [Funzione GetObjectText](getobjecttext.md) | Restituisce un rendering testuale di un oggetto nella sintassi MOF. | 
| [GetPropertyHandle (funzione)](getpropertyhandle.md) | Restituisce un handle univoco che identifica una proprietà. |
| [GetPropertyOrigin (funzione)](getpropertyorigin.md) | Determina la classe in cui viene dichiarata una proprietà. |
| [GetPropertyQualifierSet (funzione)](getpropertyqualifierset.md) | Recupera il qualificatore impostato per una particolare proprietà.  |
| [GetQualifierSet (funzione)](getqualifierset.md) | Recupera il qualificatore impostato per un'istanza della classe o una definizione di classe. |
| [InheritsFrom (funzione)](inheritsfrom.md) | Determina se la classe o istanza corrente deriva da una classe padre specificata. |
| [Initialize (funzione)](initialize.md) | Esegue l'inizializzazione di WMI. |
| [Funzione successiva](next.md) | Recupera la proprietà successiva in un'enumerazione. | 
| [NextMethod (funzione)](nextmethod.md) | Recupera il metodo successivo nell'enumerazione. |
| [Put (funzione)](put.md) | Imposta una proprietà denominata su un nuovo valore. |
| [PutClassWmi (funzione)](putclasswmi.md) | Crea una nuova classe o aggiorna uno esistente. |
| [PutInstanceWmi (funzione)](putinstancewmi.md) | Crea o aggiorna un'istanza di una classe esistente. L'istanza viene scritto il repository WMI. |
| [PutMethod (funzione)](putmethod.md) | Crea un metodo. |
| [QualifierSet_BeginEnumeration (funzione)](qualifierset-beginenumeration.md) | Reimposta l'enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione. |
| [QualifierSet_Delete (funzione)](qualifierset-delete.md) | Elimina un qualificatore specificato in base al nome.  |
| [QualifierSet_EndEnumeration (funzione)](qualifierset-endenumeration.md) | Termina l'enumerazione iniziato con una chiamata al `QualifierSet_BeginEnumeration` (funzione). |
| [QualifierSet_Get (funzione)](qualifierset-get.md) | Ottiene il qualificatore denominato specificato.  |
| [QualifierSet_GetNames (funzione)](qualifierset-getnames.md) | Recupera i nomi di tutti i qualificatori di qualificatori specificati che sono disponibili dall'oggetto corrente o dalla proprietà. |
| [QualifierSet_Next (funzione)](qualifierset-next.md) | Recupera il qualificatore di un'enumerazione che ha avviato con una chiamata al successivo il [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (funzione). |
| [QualifierSet_Put (funzione)](qualifierset-put.md) | Scrive il qualificatore denominato e il valore. |
| [ResetSecurity (funzione)](resetsecurity.md) | Assegna il token di rappresentazione fornito per il thread corrente. |
| [Funzione SetSecurity](setsecurity.md) | Recupera il token di rappresentazione associato al thread corrente. |
| [SpawnDerivedClass (funzione)](spawnderivedclass.md) | Crea un oggetto appena derivata da un oggetto specificato. | 
| [Funzione SpawnInstance](spawninstance.md) | Crea una nuova istanza di una classe. |   
| [VerifyClient (funzione)](verifyclientkey.md) | Assicura che la chiave client disponga di sicurezza corrette. |
| [WritePropertyValue (funzione)](writepropertyvalue.md) | Scrive un numero specificato di byte a una proprietà identificata da un handle di proprietà. |

 ## <a name="see-also"></a>Vedere anche
[Riferimenti alle API non gestite](../index.md) 