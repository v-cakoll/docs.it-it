---
title: -deterministica
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a>-deterministica

Fa sì che il compilatore genera un assembly il cui output di byte per byte è identico per le compilazioni per gli input identiche. 

## <a name="syntax"></a>Sintassi

```
-deterministic
```

## <a name="remarks"></a>Note

Per impostazione predefinita, l'output del compilatore da un set specificato di input sia univoco, poiché il compilatore aggiunge un timestamp e un GUID generato da numeri casuali. Utilizzare la `-deterministic` opzione per generare un *assembly deterministica*, uno cui contenuto binario è identica tra compilazioni, purché l'input rimane invariato.

Il compilatore considera i seguenti input allo scopo di determinismo:

- La sequenza di parametri della riga di comando.
- Il contenuto del file di risposta del compilatore rsp.
- La versione precisa usata dal compilatore e il relativo assembly di riferimento.
- Il percorso della directory corrente.
- Il contenuto binario di tutti i file in modo esplicito passato al compilatore direttamente o indirettamente, tra cui: 
    - File di origine
    - assembly di riferimento
    - Moduli di cui viene fatto riferimento
    - Risorse
    - Il file di chiave con nome sicuro
    - @ file di risposta
    - Analizzatori
    - Set di regole
    - File aggiuntivi che possono essere usati dagli analizzatori
- Le impostazioni cultura correnti (per la lingua in cui la diagnostica e l'eccezione vengono generati messaggi).
- La codifica predefinita (o la tabella codici corrente) se non è specificata la codifica.
- L'esistenza non esistenza e contenuto dei file nei percorsi di ricerca del compilatore (specificato, ad esempio, tramite `/lib` o `/recurse`).
- La piattaforma CLR in cui viene eseguito il compilatore.
- Il valore di `%LIBPATH%`, che possono influenzare il caricamento di dipendenza analyzer.

Quando le origini sono disponibile pubblicamente, compilazione deterministica può essere utilizzata per stabilire se un file binario viene compilato da una fonte attendibile. Può anche essere utile in un sistema di compilazione continua per determinare se è necessario eseguire le istruzioni di compilazione che dipendono dalle modifiche apportate a un file binario. 

## <a name="see-also"></a>Vedere anche
[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
[Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
