---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f81b578c5ee3ffd830cef237fba2272eecd07642
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileName`|Il percorso del file manifesto personalizzato.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il compilatore Visual Basic consente di incorporare un manifesto dell'applicazione che specifica un livello di esecuzione richiesto asInvoker. Viene creato il manifesto nella stessa cartella in cui il file eseguibile viene compilato, in genere la cartella bin\Debug o bin\Release quando si utilizza Visual Studio. Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto highestAvailable o requireAdministrator, di utilizzare questa opzione per specificare il nome del file.  
  
> [!NOTE]
>  Questa opzione e il [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) opzione si escludono a vicenda. Se si tenta di utilizzare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.  
  
 Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista. Per ulteriori informazioni sulla virtualizzazione, vedere [distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 L'applicazione sarà soggetta a virtualizzazione in presenza di una delle condizioni seguenti:  
  
1.  Utilizzare il `-nowin32manifest` opzione e non fornisce un manifesto in una successiva istruzione di compilazione o come parte di un file di risorse di Windows (. res) utilizzando il `-win32resource` opzione.  
  
2.  Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.  
  
 Visual Studio crea un file manifesto predefinito e lo archivia nella directory di debug e rilascio insieme al file eseguibile. È possibile visualizzare o modificare il file app. manifest predefinito facendo **Visualizza impostazioni di controllo dell'account utente** sul **applicazione** scheda della finestra di progettazione. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 È possibile fornire il manifesto dell'applicazione come passaggio post-compilazione personalizzato o come parte di un file di risorse Win32 usando il `-nowin32manifest` opzione. Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista. Ciò impedirà al compilatore di creare e incorporare un manifesto predefinito nel file PE.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il manifesto predefinito che il compilatore Visual Basic inserisce in un file PE.  
  
> [!NOTE]
>  Il compilatore inserisce un nome di applicazione standard MyApplication. app nel manifesto XML. Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
