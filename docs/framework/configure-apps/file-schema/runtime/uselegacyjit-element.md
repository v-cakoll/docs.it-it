---
title: <useLegacyJit> Elemento
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a467599084f01b1a48c95c5e25fb1f869156dffa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278759"
---
# <a name="uselegacyjit-element"></a>\<useLegacyJit > elemento

Determina se Common Language Runtime usa il compilatore JIT a 64 bit legacy per la compilazione JIT.  
  
\<configuration>  
\<runtime>  
\<useLegacyJit>
  
## <a name="syntax"></a>Sintassi  
  
```xml
<useLegacyJit enabled=0|1 />
```

Il nome dell'elemento `useLegacyJit` tra maiuscole e minuscole.
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
| Attributo | Descrizione                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Attributo obbligatorio.<br><br>Specifica se il runtime usa il compilatore JIT a 64 bit legacy. |  
  
### <a name="enabled-attribute"></a>attributo Enabled  
  
| Value | Descrizione                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Common language runtime usa il nuovo compilatore JIT a 64 bit incluso in .NET Framework 4.6 e versioni successive. |  
| 1     | Common language runtime usa il compilatore JIT a 64 bit precedente.                                                     |  
  
### <a name="child-elements"></a>Elementi figlio

nessuno
  
### <a name="parent-elements"></a>Elementi padre  
  
| Elemento         | Descrizione                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |  
| `runtime`       | Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.                                                        |  
  
## <a name="remarks"></a>Note  

A partire da .NET Framework 4.6, common language runtime usa un nuovo compilatore a 64 bit per la compilazione JIT (JIT) per impostazione predefinita. In alcuni casi, ciò potrebbe comportare una differenza nel comportamento dal codice dell'applicazione che è stato compilato tramite JIT dalla versione precedente del compilatore JIT a 64 bit. Impostando il `enabled` attributo del `<useLegacyJit>` elemento `1`, è possibile disabilitare il nuovo compilatore JIT a 64 bit e compilare invece l'app usando il compilatore JIT a 64 bit legacy.  
  
> [!NOTE]
> Il `<useLegacyJit>` elemento interessa solo la compilazione JIT a 64 bit. La compilazione con il compilatore JIT a 32 bit non è interessata.  
  
Invece di usare un file di configurazione, è possibile abilitare il compilatore JIT a 64 bit legacy in altri due modi:  
  
- L'impostazione di una variabile di ambiente

  Impostare il `COMPLUS_useLegacyJit` variabile di ambiente a una delle due `0` (usare il nuovo compilatore JIT a 64 bit) o `1` (usare il compilatore JIT a 64 bit precedente):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  La variabile di ambiente presenta *ambito globale*, vale a dire che influisce su tutte le applicazioni eseguite nel computer. Se impostato, è possibile eseguirne l'override dall'impostazione di file di configurazione dell'applicazione. Nome della variabile di ambiente non distinzione maiuscole/minuscole.
  
- Aggiunta di una chiave del Registro di sistema

  È possibile abilitare il compilatore JIT a 64 bit legacy aggiungendo un `REG_DWORD` valore per entrambi i `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` o `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` chiave del Registro di sistema. Il valore è denominato `useLegacyJit`. Se il valore è 0, viene utilizzato il nuovo compilatore. Se il valore è 1, il compilatore JIT a 64 bit legacy è abilitato. Il nome del valore del Registro di sistema non distinzione maiuscole/minuscole.
  
  Il valore per l'aggiunta di `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` chiave influisce su tutte le App in esecuzione nel computer. Il valore per l'aggiunta di `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` chiave influisce su tutte le app eseguite dall'utente corrente. Se un computer è configurato con più account utente, sono interessate solo le app eseguite dall'utente corrente, a meno che il valore viene aggiunto per le chiavi del Registro di sistema per anche altri utenti. Aggiunta di `<useLegacyJit>` elemento in un file di configurazione sostituisce le impostazioni del Registro di sistema, se sono presenti.  
  
## <a name="example"></a>Esempio  

File di configurazione seguente disabilita la compilazione con il nuovo compilatore JIT a 64 bit e Usa invece il compilatore JIT a 64 bit legacy.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [\<runtime > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [Mitigazione: Nuovo compilatore JIT a 64 bit](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
