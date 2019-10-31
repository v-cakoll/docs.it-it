---
title: <ThrowUnobservedTaskExceptions> Elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: 99eef6b8c264e21df7f4ecf9fc79dc607d484a0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115416"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<elemento > ThrowUnobservedTaskExceptions
Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<ThrowUnobservedTaskExceptions >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se le eccezioni di attività non gestite devono comportare l'arresto del processo in esecuzione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non termina il processo in esecuzione per un'eccezione di attività non gestita. Questa è l'impostazione predefinita.|  
|`true`|Termina il processo in esecuzione per un'eccezione di attività non gestita.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
|||  
  
## <a name="remarks"></a>Note  
 Se un'eccezione associata a un oggetto <xref:System.Threading.Tasks.Task> non è stata osservata, non esiste alcuna operazione <xref:System.Threading.Tasks.Task.Wait%2A>, l'elemento padre non è associato, la proprietà <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> non è stata letta e l'eccezione di attività viene considerata non osservata.  
  
 Nel .NET Framework 4, per impostazione predefinita, se una <xref:System.Threading.Tasks.Task> con un'eccezione non osservata viene sottoposta a Garbage Collection, il finalizzatore genera un'eccezione e termina il processo. L'interruzione del processo è determinata dall'intervallo di Garbage Collection e finalizzazione.  
  
 Per semplificare la scrittura di codice asincrono in base alle attività da parte degli sviluppatori, il .NET Framework 4,5 modifica questo comportamento predefinito per le eccezioni non osservate. Le eccezioni non osservate comportano ancora la generazione dell'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, ma, per impostazione predefinita, il processo non viene terminato. Invece, l'eccezione viene ignorata dopo la generazione dell'evento, indipendentemente dal fatto che l'eccezione venga rilevata da un gestore eventi.  
  
 Nel .NET Framework 4,5, è possibile usare l' [elemento > di\<ThrowUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) in un file di configurazione dell'applicazione per abilitare il comportamento .NET Framework 4 della generazione di un'eccezione.  
  
 Il comportamento dell'eccezione può anche essere specificato in uno dei modi seguenti:  
  
- Impostando la variabile di ambiente `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- Impostando il valore DWORD del registro di sistema ThrowUnobservedTaskExceptions = 1 nella\\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft. Chiave di NETFramework.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare la generazione di eccezioni nelle attività tramite un file di configurazione dell'applicazione.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata la modalità di generazione di un'eccezione non osservata da parte di un'attività. Il codice deve essere eseguito come programma rilasciato per funzionare correttamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
