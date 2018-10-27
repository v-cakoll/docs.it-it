---
title: -resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: ca9aea526d1039c09883696ed2a35ed930c92872
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044788"
---
# <a name="-resource-visual-basic"></a>-resource (Visual Basic)
Incorpora una risorsa gestita in un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`filename`|Obbligatorio. Il nome del file di risorse da incorporare nel file di output. Per impostazione predefinita, `filename` è pubblico nell'assembly. Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.|  
|`identifier`|Facoltativo. Il nome logico della risorsa nome utilizzato per caricarlo. L'impostazione predefinita corrisponde al nome del file. Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come con il codice seguente: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Note  
 Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.  
  
 Se `filename` è un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri di <xref:System.Resources> dello spazio dei nomi (vedere <xref:System.Resources.ResourceManager> per altre informazioni). Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei seguenti metodi: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma breve di `-resource` è `-res`.  
  
 Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle applicazioni alle risorse (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e il file di risorse consente di collegare `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
