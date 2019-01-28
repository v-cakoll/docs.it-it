---
title: -doc (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: baf0084e6caa3fce8ca8c375bdcc2bcd135fa21e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646802"
---
# <a name="-doc-c-compiler-options"></a>-doc (opzioni del compilatore C#)
L'opzione **-doc** consente di inserire commenti per la documentazione in un file XML.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 File di output in XML, con i commenti presenti nei file del codice sorgente della compilazione.  
  
## <a name="remarks"></a>Note  
 Nei file del codice sorgente è possibile elaborare e aggiungere al file XML i commenti di documentazione che precedono quanto segue:  
  
-   Tipi definiti dall'utente, ad esempio una [classe](../../../csharp/language-reference/keywords/class.md), un [delegato](../../../csharp/language-reference/keywords/delegate.md) o un'[interfaccia](../../../csharp/language-reference/keywords/interface.md)  
  
-   Membri quali un campo, un [evento](../../../csharp/language-reference/keywords/event.md), una [proprietà](../../../csharp/programming-guide/classes-and-structs/using-properties.md) o un metodo  
  
 Il primo output inserito nel file XML è quello del file di codice sorgente che contiene Main.  
  
 Per usare il file XML generato con la funzionalità [IntelliSense](/visualstudio/ide/using-intellisense), assegnare al file XML lo stesso nome dell'assembly che si vuole supportare, quindi accertarsi che il file XML si trovi nella stessa directory dell'assembly. In questo modo, quando si farà riferimento all'assembly nel progetto Visual Studio, verrà trovato anche il file XML. Per altre informazioni, vedere [Inserimento di commenti al codice XML](/visualstudio/ide/supplying-xml-code-comments).  
  
 A meno che non si esegua la compilazione con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), in `file` saranno inclusi i tag \<assembly>\</assembly> che specificano il nome del file contenente il manifesto assembly per il file di output della compilazione.  
  
> [!NOTE]
>  L'opzione -doc può essere usata per tutti i file di input o, se definita in Impostazioni progetto, per tutti i file di un progetto. Per disabilitare la visualizzazione degli avvisi relativi ai commenti di documentazione per una sezione di codice o un file specifico, usare [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Per informazioni sulla generazione di documentazione da commenti presenti nel codice, vedere [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla scheda **Generazione**.  
  
3.  Modificare la proprietà **File di documentazione XML**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
