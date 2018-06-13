---
title: Informazioni di riferimento di global.json
description: Esaminare lo schema per il file global.json, che consente di impostare la versione degli strumenti di .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33209970"
---
# <a name="globaljson-reference"></a>Informazioni di riferimento di global.json

Il file *global.json* consente di selezionare la versione degli strumenti di .NET Core usata nella proprietà `sdk`.

Gli strumenti CLI di .NET Core cercano questo file nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.

## <a name="sdk"></a>SDK
Tipo: Object

Specifica le informazioni sull'SDK.

### <a name="version"></a>version
Tipo: String

La versione dell'SDK da usare.

Ad esempio:

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
