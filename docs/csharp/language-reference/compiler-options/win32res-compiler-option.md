---
title: -win32res (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32res
dev_langs:
- CSharp
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4552b526767584e62106b2b10f8a1e6394a23b46
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="win32res-c-compiler-options"></a>/win32res (opzioni del compilatore C#)
L'opzione **/win32res** inserisce una risorsa Win32 nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/win32res:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Il file di risorse da aggiungere al file di output.  
  
## <a name="remarks"></a>Note  
 Un file di risorse Win32 può essere creato con il [compilatore di risorse](http://go.microsoft.com/fwlink/?LinkId=148370). Il Compilatore di risorse viene richiamato quando si compila un programma Visual C++. Dal file .rc viene creato un file .res.  
  
 In una risorsa Win32 può essere contenute le informazioni sulla versione o sulla bitmap (icona) che consentono di identificare l'applicazione in Esplora file. Se non si specifica **/win32res**, il compilatore genererà le informazioni sulla versione in base alla versione dell'assembly.  
  
 Vedere [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (per fare riferimento a un file di risorse di .NET Framework) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (per associarlo).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3.  Fare clic sul pulsante **File di risorse** e scegliere un file usando la casella combinata.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e associare un file di risorse Win32 `rf.res` per produrre `in.exe`:  
  
```console  
csc /win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

