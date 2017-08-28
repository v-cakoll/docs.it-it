---
title: -warnaserror (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /warnaserror
dev_langs:
- CSharp
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
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
ms.openlocfilehash: df29fd760e0e4a002f1b5078d85370a74f322e23
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="warnaserror-c-compiler-options"></a>/warnaserror (opzioni del compilatore C#)
L'opzione **/warnaserror+** considera tutti gli avvisi come errori  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## <a name="remarks"></a>Note  
 I messaggi che in genere vengono segnalati come avvisi sono invece segnalati come errori e il processo di compilazione viene interrotto (non viene compilato alcun file di output).  
  
 Per impostazione predefinita, è attiva l'opzione **/warnaserror-**, che fa in modo che gli avvisi non impediscano la generazione di un file di output. **/warnaserror**, che equivale a **/warnaserror+**, fa in modo che gli avvisi vengano considerati errori.  
  
 Facoltativamente, se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.  
  
 Usare [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) per specificare il livello degli avvisi da visualizzare nel compilatore. Usare [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) per disabilitare determinati avvisi.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Compilazione**.  
  
3.  Modificare la proprietà **Considera gli avvisi come errori**.  
  
     Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e fare in modo che il compilatore non visualizzi gli avvisi:  
  
```console  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

