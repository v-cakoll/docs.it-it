---
title: -baseaddress (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
dev_langs:
- CSharp
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
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
ms.openlocfilehash: 91193ae794957b5045a225614d6322e86d18d459
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="baseaddress-c-compiler-options"></a>/baseaddress (opzioni del compilatore C#)
L'opzione **/baseaddress** specifica l'indirizzo di base preferenziale in cui caricare una DLL. Per altre informazioni su quando e perché usare questa opzione, vedere [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) (Miglioramento dei tempi di avvio dell'applicazione) e il [blog di Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Argomenti  
 `address`  
 Indirizzo di base per la DLL. Questo indirizzo può essere specificato come numero decimale, esadecimale o ottale.  
  
## <a name="remarks"></a>Note  
 L'indirizzo di base predefinito per una DLL viene impostato dal Common Language Runtime di .NET Framework.  
  
 Tenere presente che la parola di ordine inferiore in questo indirizzo verrà arrotondata. Ad esempio, se si specifica 0x11110001, il valore verrà arrotondato a 0x11110000.  
  
 Per completare il processo di firma di una DLL, usare SN.EXE con l'opzione -R.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Compilazione**.  
  
3.  Fare clic su **Avanzate** .  
  
4.  Modificare la proprietà **Indirizzo di base DLL**.  
  
     Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName>   
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

