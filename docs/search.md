---
layout: default
title: Frontend da Solução
nav_order: 7
---

# Frontend da Solução
{: .no_toc }

### Frontend da Solução

O frontend da solução é crucial para a interação do usuário com o sistema que prevê casos de dengue no Brasil. Ele foi desenvolvido para ser intuitivo e responsivo, utilizando tecnologias modernas que garantem uma excelente experiência de usuário.

#### Tecnologias Utilizadas

- **Flutter**: Utilizado para o desenvolvimento de aplicações móveis multiplataforma, permitindo a criação de interfaces nativas para Android e iOS a partir de uma única base de código.

- **Dart**: Linguagem de programação que acompanha o Flutter, utilizada para desenvolver a lógica do aplicativo.

- **JavaScript**: Empregado para funcionalidades adicionais e interações dinâmicas no frontend.

#### Componentes do Frontend

- **Interface do Usuário (UI)**: A UI, desenvolvida com Flutter, é projetada para ser responsiva e intuitiva, facilitando a navegação do usuário através das diversas funcionalidades do aplicativo.

- **Integração com API**: O frontend se comunica com o backend através de chamadas à API, definidas no API Gateway, para operações como login, visualização de dados e envio de informações.

- **Gerenciamento de Estado**: É feito de forma eficiente para garantir a sincronização de dados entre a UI e o backend, proporcionando uma experiência de usuário consistente.



#### Código (parte do código)
{: .no_toc }
```python
import 'package:dengue_dashboard/core/data_persist_service.dart';
import 'package:dengue_dashboard/modules/constants/region_const.dart';
import 'package:flutter/material.dart';

class DropdownMenuRegion extends StatefulWidget {
  const DropdownMenuRegion({super.key});

  @override
  State<DropdownMenuRegion> createState() => _DropdownMenuRegionState();
}

class _DropdownMenuRegionState extends State<DropdownMenuRegion> {
  String dropdownValue = listRegion.first;

  @override
  Widget build(BuildContext context) {
    return DropdownMenu<String>(
      label: const Text('Região'),
      initialSelection: listRegion.first,
      onSelected: (String? value) async {
        setState(() {
          dropdownValue = value!;
        });
        await insertData(3, 'regiao', value);
      },
      dropdownMenuEntries:
          listRegion.map<DropdownMenuEntry<String>>((String value) {
        return DropdownMenuEntry<String>(value: value, label: value);
      }).toList(),
    );
  }
}
```


#### Fluxo de Trabalho

1. **Inicialização**: O aplicativo é iniciado e carrega a interface principal. Flutter assegura que a UI seja responsiva e se adapte a diferentes tamanhos de tela.

2. **Autenticação**: Usuários autenticam-se no sistema através de uma interface de login. Credenciais são verificadas por meio de chamadas à API no backend.

3. **Interação com Dados**: Após a autenticação, os usuários podem acessar funcionalidades como visualização de dados, relatórios e gráficos. Essas interações são geridas pelo backend via chamadas de API.

4. **Atualização de Dados**: Usuários podem enviar novas informações ou atualizar dados existentes. Essas operações são realizadas via chamadas à API, garantindo que os dados no backend estejam sempre atualizados.

5. **Notificações e Feedback**: O frontend fornece feedback em tempo real para o usuário, como confirmações de operações bem-sucedidas ou notificações de erros, utilizando mecanismos de UI do Flutter.

#### Benefícios

- **Desenvolvimento Multiplataforma**: Flutter permite o desenvolvimento de uma única base de código para múltiplas plataformas, reduzindo o tempo e esforço de desenvolvimento.

- **Experiência de Usuário Consistente**: Interface intuitiva e responsiva que garante uma experiência agradável para o usuário.

- **Integração Eficiente com Backend**: Comunicação fluida entre frontend e backend através de APIs bem definidas, garantindo que os dados estejam sempre sincronizados e atualizados.

Essa abordagem proporciona uma solução de frontend robusta e eficiente, garantindo que os usuários tenham uma experiência de alta qualidade ao interagir com o sistema, especialmente ao prever casos de dengue no Brasil.

Para mais detalhes, você pode acessar o repositório do projeto no [GitHub](https://github.com/FranklinAurelio/Engenharia_de_software_PPGCC).
