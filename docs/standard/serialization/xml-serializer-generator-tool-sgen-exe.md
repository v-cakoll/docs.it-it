---
title: Strumento per la generazione di serializzatori XML (Sgen.exe)
description: Il generatore di serializzatori XML crea un assembly di serializzazione XML per i tipi in un assembly, che migliora le prestazioni di avvio di XmlSerializer.
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: b6d9406ca6a69f7bdff3129b55c89dd5d1589d3f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288940"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>Strumento per la generazione di serializzatori XML (Sgen.exe)

Il generatore di serializzatori XML crea un assembly di serializzazione XML per i tipi in un assembly specificato. L'assembly di serializzazione migliora le prestazioni di avvio di una classe <xref:System.Xml.Serialization.XmlSerializer> durante la serializzazione o la deserializzazione di oggetti dei tipi specificati.
  
## <a name="syntax"></a>Sintassi

Eseguire lo strumento dalla riga di comando.
  
```console  
sgen [options]  
```
  
> [!TIP]
> Per il corretto funzionamento degli strumenti di .NET Framework, è necessario `Path` impostare `Include` correttamente le `Lib` variabili di ambiente, e. Impostare queste variabili di ambiente eseguendo SDKVars. bat, che si trova nella \<SDK> directory \v2.0\Bin SDKVars.bat deve essere eseguito in ogni shell di comandi.
  
## <a name="parameters"></a>Parametri  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/a \[ ssembly \] :**_nomefile_|Genera il codice di serializzazione per tutti i tipi contenuti nell'assembly o nell'eseguibile specificato da *nomefile*. È possibile indicare un solo nome file. Se questo argomento viene ripetuto, verrà utilizzato l'ultimo nome file.|  
|**/c \[ ompiler \] :**_Opzioni_|Specifica l'opzione da passare al compilatore C#. Tutte le opzioni di csc.exe vengono supportate dopo essere state passate al compilatore. Questa opzione può essere utilizzata per specificare che l'assembly deve essere firmato e per indicare il file di chiave.|  
|**/d \[ ebug\]**|Genera un'immagine utilizzabile con un debugger.|  
|**/f \[ forza\]**|Impone la sovrascrittura di un assembly esistente con lo stesso nome. Il valore predefinito è **false**.|  
|**/Help o/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**\[Eni/k\]**|Impedisce l'eliminazione dei file di origine generati e di altri file temporanei al termine della compilazione nell'assembly di serializzazione. Questa opzione può essere utilizzata per determinare se lo strumento genera codice di serializzazione per un determinato tipo.|  
|**/n \[ ologo\]**|Elimina la visualizzazione del messaggio di avvio Microsoft.|  
|**/o \[ ut \] :**_percorso_|Specifica la directory in cui salvare l'assembly generato. **Nota:** il nome dell'assembly generato è composto dal nome dell'assembly di input e da "xmlSerializers.dll".|  
|**/p \[ roxytypes\]**|Genera codice di serializzazione solo per i tipi proxy del servizio Web XML.|  
|**/r \[ eference \] :**_AssemblyFiles_|Specifica gli assembly a cui fanno riferimento i tipi che richiedono la serializzazione XML. Accetta più file di assembly separati da virgole.|  
|**/s \[ ilent\]**|Evita la visualizzazione dei messaggi di operazione riuscita.|  
|**/t \[ IPO \] :**_tipo_|Genera codice di serializzazione solo per il tipo specificato.|  
|**/v \[ erbose\]**|Visualizza output dettagliato per il debug. Elenca i tipi dell'assembly di destinazione che non possono essere serializzati con <xref:System.Xml.Serialization.XmlSerializer>.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Osservazioni  
 Quando lo strumento per la generazione di serializzatori XML non viene utilizzato, un oggetto <xref:System.Xml.Serialization.XmlSerializer> genera codice e un assembly di serializzazione per ogni tipo ogni volta che viene eseguita un'applicazione. Per migliorare le prestazioni dell'avvio della serializzazione XML, utilizzare lo strumento Sgen. exe per generare in anticipo tali assembly. Tali assembly potranno quindi essere distribuiti insieme all'applicazione.  
  
 Lo strumento per la generazione di serializzatori XML può inoltre migliorare le prestazioni dei client che utilizzano i proxy del servizio Web XML per comunicare con i server, in quanto il processo di serializzazione non influisce sulle prestazioni quando il tipo viene caricato per la prima volta.  
  
 Gli assembly generati non possono essere utilizzati sul lato server di un servizio Web. Questo strumento è destinato esclusivamente ai client del servizio Web e agli scenari di serializzazione manuale.  
  
 Se l'assembly contenente il tipo da serializzare è denominato MyType.dll, l'assembly di serializzazione associato verrà denominato MyType.XmlSerializers.dll.  
  
## <a name="examples"></a>Esempi  
 Il comando seguente crea un assembly denominato Data.XmlSerializers.dll per la serializzazione di tutti i tipi contenuti nell'assembly denominato Data.dll.  
  
```console  
sgen Data.dll
```  
  
 Il codice che deve serializzare e deserializzare i tipi in Data.dll può fare riferimento all'assembly Data.XmlSerializers.dll.  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](../../framework/tools/index.md)
- [Prompt dei comandi](../../framework/tools/developer-command-prompt-for-vs.md)
