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
ms.openlocfilehash: 01ea71f3de9e30abe25184e38a59f3707b54bd5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73422965"
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
  
## <a name="remarks"></a>Osservazioni  
 Nei file del codice sorgente è possibile elaborare e aggiungere al file XML i commenti di documentazione che precedono quanto segue:  
  
- Tipi definiti dall'utente, ad esempio una [classe](../keywords/class.md), un [delegato](../builtin-types/reference-types.md#the-delegate-type) o un'[interfaccia](../keywords/interface.md)  
  
- Membri quali un campo, un [evento](../keywords/event.md), una [proprietà](../../programming-guide/classes-and-structs/using-properties.md) o un metodo  
  
 Il primo output inserito nel file XML è quello del file di codice sorgente che contiene Main.  
  
 Per usare il file XML generato con la funzionalità [IntelliSense](/visualstudio/ide/using-intellisense), assegnare al file XML lo stesso nome dell'assembly che si vuole supportare, quindi accertarsi che il file XML si trovi nella stessa directory dell'assembly. In questo modo, quando si farà riferimento all'assembly nel progetto Visual Studio, verrà trovato anche il file XML. Per altre informazioni, vedere [Inserimento di commenti al codice XML](/visualstudio/ide/reference/generate-xml-documentation-comments).  
  
 A meno che non si esechi \<la compilazione con [-target:module](./target-module-compiler-option.md), `file` conterrà \<i tag>assembly /assembly> che specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.  
  
> [!NOTE]
> L'opzione -doc può essere usata per tutti i file di input o, se definita in Impostazioni progetto, per tutti i file di un progetto. Per disabilitare la visualizzazione degli avvisi relativi ai commenti di documentazione per una sezione di codice o un file specifico, usare [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Per informazioni sulla generazione di documentazione da commenti presenti nel codice, vedere [Tag consigliati per i commenti relativi alla documentazione](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla scheda **Generazione**.  
  
3. Modificare la proprietà **File di documentazione XML**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
