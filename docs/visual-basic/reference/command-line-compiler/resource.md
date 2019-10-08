---
title: -Resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005199"
---
# <a name="-resource-visual-basic"></a>-Resource (Visual Basic)
Incorpora una risorsa gestita in un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

oppure  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`filename`|Obbligatorio. Nome del file di risorse da incorporare nel file di output. Per impostazione predefinita, `filename` è pubblico nell'assembly. Racchiudere il nome file tra virgolette ("") se contiene uno spazio.|  
|`identifier`|facoltativo. Nome logico della risorsa. nome usato per caricarlo. L'impostazione predefinita corrisponde al nome del file. Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come nel seguente esempio: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Note  
 Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.  
  
 Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi con membri nello spazio dei nomi <xref:System.Resources> (per altre informazioni, vedere <xref:System.Resources.ResourceManager>). Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei metodi seguenti: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma breve di `-resource` è `-res`.  
  
 Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e connette il file di risorse `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
