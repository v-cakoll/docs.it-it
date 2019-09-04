---
title: <useLegacyJit> Elemento
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b783a82b1ef964de308532ef544bbfab2397400
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252230"
---
# <a name="uselegacyjit-element"></a>Elemento \<useLegacyJit>

Determina se Common Language Runtime usa il compilatore JIT a 64 bit legacy per la compilazione JIT.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<useLegacyJit>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<useLegacyJit enabled=0|1 />
```

Il nome `useLegacyJit` dell'elemento fa distinzione tra maiuscole e minuscole.
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
| Attributo | Descrizione                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Attributo obbligatorio.<br><br>Specifica se il runtime usa il compilatore JIT a 64 bit legacy. |  
  
### <a name="enabled-attribute"></a>attributo enabled  
  
| Value | Descrizione                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Il Common Language Runtime usa il nuovo compilatore JIT a 64 bit incluso in .NET Framework 4,6 e versioni successive. |  
| 1     | Il Common Language Runtime usa il compilatore JIT a 64 bit precedente.                                                     |  
  
### <a name="child-elements"></a>Elementi figlio

Nessuna
  
### <a name="parent-elements"></a>Elementi padre  
  
| Elemento         | Descrizione                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |  
| `runtime`       | Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.                                                        |  
  
## <a name="remarks"></a>Note  

A partire da .NET Framework 4,6, il Common Language Runtime usa un nuovo compilatore a 64 bit per la compilazione JIT (just-in-Time) per impostazione predefinita. In alcuni casi, questo può comportare una differenza nel comportamento del codice dell'applicazione compilato tramite JIT dalla versione precedente del compilatore JIT a 64 bit. Impostando l' `enabled` attributo `<useLegacyJit>` dell'elemento su, `1`è possibile disabilitare il nuovo compilatore JIT a 64 bit e compilare l'app usando il compilatore JIT legacy a 64 bit.  
  
> [!NOTE]
> L' `<useLegacyJit>` elemento interessa solo la compilazione JIT a 64 bit. La compilazione con il compilatore JIT a 32 bit non è interessata.  
  
Invece di usare un'impostazione del file di configurazione, è possibile abilitare il compilatore JIT a 64 bit legacy in altri due modi:  
  
- Impostazione di una variabile di ambiente

  Impostare la `COMPLUS_useLegacyJit` variabile `0` di ambiente su (usare il nuovo compilatore JIT a 64 bit) o `1` (usare il compilatore JIT a 64 bit precedente):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  La variabile di ambiente ha *ambito globale*, il che significa che ha effetto su tutte le applicazioni eseguite nel computer. Se impostato, è possibile eseguire l'override dell'impostazione del file di configurazione dell'applicazione. Il nome della variabile di ambiente non distingue tra maiuscole e minuscole.
  
- Aggiunta di una chiave del registro di sistema

  È possibile abilitare il compilatore JIT a 64 bit legacy aggiungendo un `REG_DWORD` valore alla `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` chiave o `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` nel registro di sistema. Il valore è denominato `useLegacyJit`. Se il valore è 0, viene utilizzato il nuovo compilatore. Se il valore è 1, il compilatore JIT a 64 bit legacy è abilitato. Il nome del valore del registro di sistema non distingue tra maiuscole e minuscole.
  
  L'aggiunta del valore alla `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` chiave influiscono su tutte le app in esecuzione nel computer. L'aggiunta del valore alla `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` chiave influiscono su tutte le app eseguite dall'utente corrente. Se un computer è configurato con più account utente, vengono interessate solo le app eseguite dall'utente corrente, a meno che il valore non venga aggiunto anche alle chiavi del registro di sistema per altri utenti. L'aggiunta `<useLegacyJit>` dell'elemento a un file di configurazione sostituisce le impostazioni del registro di sistema, se presenti.  
  
## <a name="example"></a>Esempio  

Il file di configurazione seguente disabilita la compilazione con il nuovo compilatore JIT a 64 bit e usa invece il compilatore JIT legacy a 64 bit.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [\<Elemento runtime >](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
- [Mitigazione Nuovo compilatore JIT a 64 bit](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
