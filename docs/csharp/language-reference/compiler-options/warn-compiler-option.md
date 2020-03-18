---
title: -warn (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602401"
---
# <a name="-warn-c-compiler-options"></a>-warn (opzioni del compilatore C#)
L'opzione **-warn** specifica il livello di avviso da visualizzare nel compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Argomenti  
 `option`  
 Livello di avviso da visualizzare per la compilazione: i numeri più bassi mostrano solo gli avvisi con un livello di gravità elevato, i valori più alti mostrano altri avvisi. I valori validi sono 0-4:  
  
|Livello avvisi|Significato|  
|-------------------|-------------|  
|0|Disattiva l'emissione di tutti i messaggi di avviso.|  
|1|Visualizza i messaggi di avviso gravi.|  
|2|Visualizza gli avvisi di livello 1 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi ai membri di classi nascosti.|  
|3|Visualizza gli avvisi di livello 2 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi alle espressioni che restituiscono sempre `true` o `false`.|  
|4 (impostazione predefinita)|Visualizza tutti gli avvisi di livello 3 oltre ad avvisi informativi.|  
  
## <a name="remarks"></a>Osservazioni  
 Per ottenere informazioni su un errore o un avviso, è possibile cercare il codice di errore nell'indice della Guida. Per altri modi per ottenere informazioni su un errore o un avviso, vedere [Errori del compilatore C#](../compiler-messages/index.md).  
  
 Usare [-warnaserror](./warnaserror-compiler-option.md) per considerare tutti gli avvisi come errori. Usare [-nowarn](./nowarn-compiler-option.md) per disabilitare avvisi specifici.  
  
 **-w** è la versione abbreviata di **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Modificare la proprietà **Livello avvisi**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e fare in modo che il compilatore visualizzi solo gli avvisi di livello 1:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
