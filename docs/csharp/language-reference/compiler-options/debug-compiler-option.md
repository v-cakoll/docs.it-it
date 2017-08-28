---
title: -debug (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /debug
dev_langs:
- CSharp
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
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
ms.openlocfilehash: 82656c8354288dd2f7e5b0dcb2905b6c050c0521
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="debug-c-compiler-options"></a>/debug (opzioni del compilatore C#)
L'opzione **/debug** indica al compilatore di generare informazioni di debug e di inserirle nel file o file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Se si specifica `+`, o soltanto **/debug**, il compilatore genera le informazioni di debug e le inserisce in un database di programma (file PDB). Se si specifica `-`, ovvero non si specifica **/debug**, non verranno create informazioni di debug.  
  
 `full` &#124; `pdbonly`  
 Specifica il tipo di informazioni di debug generate dal compilatore. L'argomento completo, che viene usato se non si specifica **/debug:pdbonly**, consente di allegare un debugger al programma in esecuzione. Specificando pdbonly si consente il debug del codice sorgente quando il programma viene avviato nel debugger, ma l'assembler viene visualizzato solo se il programma in esecuzione è allegato al debugger.  
  
## <a name="remarks"></a>Note  
 Usare questa opzione per creare build di debug. Se **/debug**, **/debug+** o **/debug:full** non è specificato, non sarà possibile eseguire il debug del file di output del programma.  
  
 Se si usa **/debug:full**, tenere presente che comporta un certo impatto sulla velocità e sulle dimensioni del codice ottimizzato JIT ed effetti minori sulla qualità del codice con **/debug: full**. Si consiglia l'uso di **/debug:pdbonly** o nessun file PDB per la generazione del codice di rilascio.  
  
> [!NOTE]
>  Una differenza tra **/debug:pdbonly** e **/debug:full** è che con **/debug:full** il compilatore genera un <xref:System.Diagnostics.DebuggableAttribute>, che viene usato per indicare al compilatore JIT che le informazioni di debug sono disponibili. Di conseguenza, si otterrà un errore se il codice contiene <xref:System.Diagnostics.DebuggableAttribute> impostato su false se si usa **/debug:full**.  
  
 Per altre informazioni su come configurare le prestazioni di debug di un'applicazione, vedere [Semplificazione del debug di un'immagine](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Per modificare il percorso del file PDB, vedere [/pdb (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Compilazione**.  
  
3.  Fare clic su **Avanzate** .  
  
4.  Modificare la proprietà **Informazioni di Debug**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Esempio  
 Inserire le informazioni di debug nel file di output `app.pdb`:  
  
```console  
csc /debug /pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

