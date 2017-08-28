---
title: -out (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /out
dev_langs:
- CSharp
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
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
ms.openlocfilehash: a6db728bc98f5223fc35268a1cce41021ff530cc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="out-c-compiler-options"></a>/out (opzioni del compilatore C#)
L'opzione **/out** specifica il nome del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/out:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Il nome del file di output creato dal compilatore.  
  
## <a name="remarks"></a>Note  
 Nella riga di comando è possibile specificare più file di output per la compilazione. Dopo l'opzione **/out** è prevista la presenza di uno o più file di codice sorgente. Tutti i file di codice sorgente verranno quindi compilati nel file di output specificato con l'opzione **/out**.  
  
 Specificare il nome completo e l'estensione del file che si vuole creare.  
  
 Se non si specifica il nome del file di output:  
  
-   Un file con estensione exe corrisponderà al nome del file di codice sorgente che contiene il metodo **Main**.  
  
-   Un file con estensione dll o netmodule corrisponderà al nome del primo file di codice sorgente.  
  
 Non è possibile usare per la compilazione di un file di output un file di codice sorgente già usato per compilare un altro file di output nella stessa compilazione.  
  
 Quando si generano più file di output in una compilazione da riga di comando, tenere presente che solo uno dei file di output può essere un assembly e che solo il primo file di output specificato (in modo implicito o esplicito con l'opzione **/out**) può essere l'assembly.  
  
 I moduli prodotti durante una compilazione diventano file associati a un assembly prodotto anch'esso in fase di compilazione. Per visualizzare il manifesto dell'assembly e i file associati, usare [ildasm.exe](https://msdn.microsoft.com/library/f7dy01k1).  
  
 L'opzione del compilatore /out è necessaria affinché un file eseguibile sia la destinazione di un assembly Friend. Per altre informazioni, vedere [Assembly Friend](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3.  Modificare la proprietà **Nome assembly**.  
  
     Per impostare l'opzione del compilatore a livello di codice: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> è una proprietà di sola lettura caratterizzata dalla combinazione del tipo di progetto (file eseguibile, libreria e così via) e del nome dell'assembly. Per impostare il nome del file di output sarà necessario modificare una o entrambe queste proprietà.  
  
## <a name="example"></a>Esempio  
 Per compilare `t.cs` e creare il file di output `t.exe`, nonché per generare `t2.cs` e creare il file di output del modulo `mymodule.netmodule`:  
  
```console  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Assembly Friend](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)   
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

