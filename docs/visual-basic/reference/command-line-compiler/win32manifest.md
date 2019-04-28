---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 15fe62457ed11ffcd08a1db3aa8be57080f22869
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774777"
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
 Per impostazione predefinita, il compilatore Visual Basic consente di incorporare un manifesto dell'applicazione che specifica un livello di esecuzione richiesto di asInvoker. Crea il manifesto nella stessa cartella in cui il file eseguibile viene compilato, in genere la cartella bin\Debug o bin\Release quando si usa Visual Studio. Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto di, requireAdministrator o highestAvailable usare questa opzione per specificare il nome del file.  
  
> [!NOTE]
>  Questa opzione e il [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) opzione si escludono a vicenda. Se si tenta di usare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.  
  
 Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista. Per altre informazioni sulla virtualizzazione, vedere [Distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 L'applicazione sarà soggetta alla virtualizzazione se viene soddisfatta una delle condizioni seguenti:  
  
1. Si utilizza il `-nowin32manifest` opzione e si specifica un manifesto in una fase successiva della compilazione o come parte di un file di risorse di Windows (res) usando il `-win32resource` opzione.  
  
2. Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.  
  
 Visual Studio crea un file manifesto predefinito e lo memorizza nelle directory di debug e versione insieme al file eseguibile. È possibile visualizzare o modificare il file app. manifest predefinito facendo **Visualizza impostazioni di controllo dell'account utente** nel **applicazione** scheda Progettazione progetti. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 È possibile fornire il manifesto dell'applicazione come passaggio post-compilazione personalizzato o come parte di un file di risorse Win32 usando il `-nowin32manifest` opzione. Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista. Ciò impedirà al compilatore di creare e incorporare un manifesto predefinito nel file PE.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente mostra il manifesto predefinito che il compilatore Visual Basic inserisce in un file PE.  
  
> [!NOTE]
>  Il compilatore inserisce un nome di applicazione standard MyApplication. app nel manifesto del XML. Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.  
  
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

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
