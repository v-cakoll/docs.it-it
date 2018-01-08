---
title: Informazioni di riferimento di global.json
description: Esaminare lo schema per il file global.json, che consente di impostare la versione degli strumenti di .NET Core.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.workload: dotnetcore
ms.openlocfilehash: c7e64995ed00a6b2df1b7e1dfa43c6bea5cf4535
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
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
