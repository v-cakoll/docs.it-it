---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349138"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileName`|The path of the custom manifest file.|  
  
## <a name="remarks"></a>Note  
 By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker. It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio. If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.  
  
> [!NOTE]
> This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive. If you try to use both options in the same command line, you will get a build error.  
  
 Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista. Per altre informazioni sulla virtualizzazione, vedere [Distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Your application will be subject to virtualization if either of the following conditions is true:  
  
1. You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.  
  
2. Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.  
  
 Visual Studio crea un file manifesto predefinito e lo memorizza nelle directory di debug e versione insieme al file eseguibile. You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option. Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista. This will prevent the compiler from creating and embedding a default manifest in the PE file.  
  
## <a name="example"></a>Esempio  
 The following example shows the default manifest that the Visual Basic compiler inserts into a PE.  
  
> [!NOTE]
> The compiler inserts a standard application name MyApplication.app into the manifest XML. Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.  
  
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
