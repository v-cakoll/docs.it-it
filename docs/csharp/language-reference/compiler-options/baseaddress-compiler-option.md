---
title: -baseaddress (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7cd3269754f783ab8b26683f5215aa81825673e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress-c-compiler-options"></a>/baseaddress (opzioni del compilatore C#)
L'opzione **/baseaddress** specifica l'indirizzo di base preferenziale in cui caricare una DLL. Per ulteriori informazioni su quando e perché utilizzare questa opzione, vedere [blog di Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
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
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
