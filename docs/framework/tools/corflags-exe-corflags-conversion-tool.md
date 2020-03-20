---
title: CorFlags.exe (strumento di conversione CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129855"
---
# <a name="corflagsexe-corflags-conversion-tool"></a>CorFlags.exe (strumento di conversione CorFlags)
Lo strumento di conversione CorFlags consente di configurare la sezione CorFlags dell'intestazione di un'immagine eseguibile di tipo PE.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro obbligatorio.|Descrizione|  
|------------------------|-----------------|  
|`assembly`|Nome dell'assembly per il quale configurare CorFlags.|  
  
|Opzione|Descrizione|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|Imposta il flag 32BITREQUIRED.|  
|`-32BIT[REQ]-`|Cancella il flag 32BITREQUIRED.|  
|`-32BITPREF+`|Imposta il flag 32BITPREFERRED. L'applicazione viene eseguita come processo a 32 bit anche sulle piattaforme a 64 bit. Impostare questo flag solo su file EXE. Se il flag viene impostato su una DLL, la DLL non viene caricata nei processi a 64 bit e viene generata un'eccezione <xref:System.BadImageFormatException>. Un file EXE con questo flag può essere caricato in un processo a 64 bit.<br /><br /> Novità di .NET Framework 4.5.|  
|`-32BITPREF-`|Cancella il flag 32BITPREFERRED.<br /><br /> Novità di .NET Framework 4.5.|  
|`-?`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|`-Force`|Forza un aggiornamento anche se l'assembly ha un nome sicuro. **Importante:** se si aggiorna un assembly con nome sicuro è necessario firmarlo nuovamente prima di eseguirne il codice.|  
|`-help`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|`-ILONLY+`|Imposta il flag ILONLY.|  
|`-ILONLY-`|Cancella il flag ILONLY.|  
|`-nologo`|Evita la visualizzazione del messaggio di avvio Microsoft.|  
|`-RevertCLRHeader`|Ripristina la versione 2.0 dell'intestazione CLR.|  
|`-UpgradeCLRHeader`|Esegue l'aggiornamento dell'intestazione CLR alla versione 2.5. **Nota:** per essere eseguiti a livello nativo, gli assembly devono disporre di un'intestazione CLR versione 2.5 o successiva.|  
  
## <a name="remarks"></a>Osservazioni  
 Se non viene specificata alcuna opzione, lo strumento di conversione CorFlags visualizza i flag relativi all'assembly specificato.  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Applicazioni a 64 bit](../64-bit-apps.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
