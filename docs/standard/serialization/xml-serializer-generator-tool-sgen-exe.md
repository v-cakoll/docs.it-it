---
title: Strumento per la generazione di serializzatori XML (Sgen.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 73669fcfd74f9c4948c8ec976ff3271c72f1033a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>Strumento per la generazione di serializzatori XML (Sgen.exe)
Lo strumento per la generazione di serializzatori XML (Sgen.exe) consente di creare un assembly di serializzazione XML per i tipi in un assembly specificato al fine di migliorare le prestazioni di avvio di un oggetto <xref:System.Xml.Serialization.XmlSerializer> quando serializza o deserializza oggetti dei tipi specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
sgen [options]  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/a**[**ssembly**]**:***nomefile*|Genera il codice di serializzazione per tutti i tipi contenuti nell'assembly o nell'eseguibile specificato da *nomefile*. È possibile indicare un solo nome file. Se questo argomento viene ripetuto, verrà utilizzato l'ultimo nome file.|  
|**/c[ompiler]:** *opzioni*|Specifica l'opzione da passare al compilatore C#. Tutte le opzioni di csc.exe vengono supportate dopo essere state passate al compilatore. Questa opzione può essere utilizzata per specificare che l'assembly deve essere firmato e per indicare il file di chiave.|  
|**/d**[**ebug**]|Genera un'immagine utilizzabile con un debugger.|  
|**/f[orce]**|Impone la sovrascrittura di un assembly esistente con lo stesso nome. Il valore predefinito è **false**.|  
|**/help o /?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/k**[**eep**]|Impedisce l'eliminazione dei file di origine generati e di altri file temporanei al termine della compilazione nell'assembly di serializzazione. Questa opzione può essere utilizzata per determinare se lo strumento genera codice di serializzazione per un determinato tipo.|  
|**/n**[**ologo**]|Elimina la visualizzazione del messaggio di avvio Microsoft.|  
|**/o**[**ut**]**:***percorso*|Specifica la directory in cui salvare l'assembly generato. **Nota:** il nome dell'assembly generato è composto dal nome dell'assembly di input e da "xmlSerializers.dll".|  
|**/p**[**roxytypes**]|Genera codice di serializzazione solo per i tipi proxy del servizio Web XML.|  
|**/r**[**eference**]**:***fileassembly*|Specifica gli assembly a cui fanno riferimento i tipi che richiedono la serializzazione XML. Accetta più file di assembly separati da virgole.|  
|**/s**[**ilent**]|Evita la visualizzazione dei messaggi di operazione riuscita.|  
|**/t**[**ype**]**:***tipo*|Genera codice di serializzazione solo per il tipo specificato.|  
|**/v**[**erbose**]|Visualizza output dettagliato per il debug. Elenca i tipi dell'assembly di destinazione che non possono essere serializzati con <xref:System.Xml.Serialization.XmlSerializer>.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Note  
 Quando lo strumento per la generazione di serializzatori XML non viene utilizzato, un oggetto <xref:System.Xml.Serialization.XmlSerializer> genera codice e un assembly di serializzazione per ogni tipo ogni volta che viene eseguita un'applicazione. Per migliorare le prestazioni dell'avvio della serializzazione XML, utilizzare lo strumento Sgen.exe per generare gli assembly in anticipo. Tali assembly potranno quindi essere distribuiti insieme all'applicazione.  
  
 Lo strumento per la generazione di serializzatori XML può inoltre migliorare le prestazioni dei client che utilizzano i proxy del servizio Web XML per comunicare con i server, in quanto il processo di serializzazione non influisce sulle prestazioni quando il tipo viene caricato per la prima volta.  
  
 Gli assembly generati non possono essere utilizzati sul lato server di un servizio Web. Questo strumento è destinato esclusivamente ai client del servizio Web e agli scenari di serializzazione manuale.  
  
 Se l'assembly contenente il tipo da serializzare è denominato MyType.dll, l'assembly di serializzazione associato verrà denominato MyType.XmlSerializers.dll.  
  
## <a name="examples"></a>Esempi  
 Il comando seguente crea un assembly denominato Data.XmlSerializers.dll per la serializzazione di tutti i tipi contenuti nell'assembly denominato Data.dll.  
  
```  
sgen Data.dll   
```  
  
 Il codice che deve serializzare e deserializzare i tipi in Data.dll può fare riferimento all'assembly Data.XmlSerializers.dll.  
  
## <a name="see-also"></a>Vedere anche  
 [Strumenti](../../../docs/framework/tools/index.md)  
 [Panoramica dei servizi Web XML](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)  
 [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
