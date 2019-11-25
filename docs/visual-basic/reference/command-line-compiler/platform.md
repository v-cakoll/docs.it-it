---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352349"
---
# <a name="-platform-visual-basic"></a>-platform (Visual Basic)
Consente di specificare la versione di Common Language Runtime (CLR) in grado di eseguire il file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a>argomenti  
  
|Termine|Definizione|  
|---|---|  
|`x86`|Compila l'assembly in modo da essere eseguito da CLR a 32 bit, compatibile con x86.|  
|`x64`|Compila l'assembly l'assemby in modo da essere eseguito da CLR a 64 bit su un computer che supporta il set di istruzioni AMD64 o EM64T.|  
|`Itanium`|Compila l'assembly in modo da essere eseguito da CLR a 64 bit su un computer dotato di processore Itanium.|  
|`arm`|Compila l'assembly in modo da essere eseguito su un computer con processore ARM (Advanced RISC Machine).|  
|`anycpu`|Compila l'assembly in modo da essere eseguito su qualsiasi piattaforma. L'applicazione verrà eseguita come applicazione a 32 bit su versioni di Windows a 32 bit e come applicazione a 64 bit su versioni di Windows a 64 bit. Questo flag è il valore predefinito.|  
|`anycpu32bitpreferred`|Compila l'assembly in modo da essere eseguito su qualsiasi piattaforma. L'applicazione verrà eseguita come applicazione a 32 bit sia nelle versioni di Windows a 32 bit che in quelle a 64 bit. This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.|  
  
## <a name="remarks"></a>Note  
 Per specificare il tipo di processore di destinazione del file di output, usare l'opzione `-platform`.  
  
 In genere, gli assembly .NET Framework scritti in Visual Basic vengono sempre eseguiti, indipendentemente dalla piattaforma. L'elaborazione di alcuni elementi può tuttavia risultare influenzata dalla piattaforma in uso. I casi più comuni sono:  
  
- Strutture contenenti membri che cambiano dimensione in base alla piattaforma, ad esempio tutti i tipi puntatore.  
  
- Operazioni aritmetiche che includono dimensioni costanti.  
  
- Dichiarazioni pInvoke o COM non corrette che usano `Integer` anziché <xref:System.IntPtr> per gli handle.  
  
- Casting di <xref:System.IntPtr> su `Integer`.  
  
- Uso dell'interoperabilità pInvoke o COM con componenti non disponibili in tutte le piattaforme.  
  
 The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on. In particolare:  
  
- Se si specifica l'opzione per una piattaforma a 64 bit e l'applicazione viene eseguita su un computer a 32 bit, il messaggio di errore verrà visualizzato con maggiore anticipo e sarà maggiormente descrittivo del problema specifico rispetto all'errore che si verifica senza usare questa opzione.  
  
- Se si imposta il flag `x86` e successivamente si usa un computer a 64 bit per l'elaborazione dell'applicazione, questa verrà eseguita nel sottosistema WOW e non a livello nativo.  
  
 In un sistema operativo Windows a 64 bit:  
  
- Gli assembly compilati con l'opzione `-platform:x86` potranno essere eseguiti da CLR a 32 bit in WOW64.  
  
- Gli eseguibili compilati con l'opzione `-platform:anycpu` potranno essere eseguiti da CLR a 64 bit.  
  
- Una DLL compilata con l'opzione `-platform:anycpu` potrà essere eseguita dallo stesso CLR del processo in cui viene caricata.  
  
- Gli eseguibili compilati con l'opzione `-platform:anycpu32bitpreferred` potranno essere eseguiti da CLR a 32 bit.  
  
 For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a>To set -platform in the Visual Studio IDE  
  
1. In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.  
  
2. On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.  
  
     For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come usare l'opzione del compilatore `-platform`.  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (Visual Basic)](target.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
