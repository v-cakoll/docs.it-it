---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 6f77649365f8ca7b163cd55854aa9960d88f2984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414259"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileName`|Percorso del file manifesto personalizzato.|  
  
## <a name="remarks"></a>Commenti  
 Per impostazione predefinita, il compilatore Visual Basic incorpora un manifesto dell'applicazione che specifica un livello di esecuzione richiesto di asInvoker. Crea il manifesto nella stessa cartella in cui viene compilato il file eseguibile, in genere la cartella bin\Debug o bin\Release quando si usa Visual Studio. Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto di highestAvailable o requireAdministrator, utilizzare questa opzione per specificare il nome del file.  
  
> [!NOTE]
> Questa opzione e l'opzione [-win32resource (](win32resource.md) si escludono a vicenda. Se si tenta di usare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.  
  
 Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista. Per altre informazioni sulla virtualizzazione, vedere [Distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 L'applicazione sarà soggetta alla virtualizzazione se si verifica una delle condizioni seguenti:  
  
1. Usare l' `-nowin32manifest` opzione e non si fornisce un manifesto in un'istruzione di compilazione successiva o come parte di un file di risorse Windows (res) tramite l' `-win32resource` opzione.  
  
2. Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.  
  
 Visual Studio crea un file manifesto predefinito e lo memorizza nelle directory di debug e versione insieme al file eseguibile. Per visualizzare o modificare il file app. manifest predefinito, fare clic su **Visualizza impostazioni UAC** nella scheda **applicazione** in Progettazione progetti. Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 È possibile fornire il manifesto dell'applicazione come passaggio di post-compilazione personalizzato o come parte di un file di risorse Win32 utilizzando l' `-nowin32manifest` opzione. Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista. In questo modo si impedisce al compilatore di creare e incorporare un manifesto predefinito nel file PE.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il manifesto predefinito inserito dal compilatore Visual Basic in un file PE.  
  
> [!NOTE]
> Il compilatore inserisce nel file XML del manifesto un nome applicazione standard MyApplication. app. Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.  
  
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

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-nowin32manifest (Visual Basic)](nowin32manifest.md)
