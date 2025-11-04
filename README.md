✨ Snippets da Extensão

Esta extensão adiciona snippets prontos para agilizar a criação de código padrão no projeto, seguindo o padrão de arquitetura do sistema ERP (Use Cases, Endpoints, Paths e Schemas Zod).

🧠 UseCase Class Template

Prefixo: usc

Cria uma classe UseCase com imports padrão e nome igual ao arquivo.

import endpoints from "src/application/utils/endpoints";
import UseCase from "../../UseCase";

export default class NomeDoArquivo extends UseCase {
    async execute() {
        // lógica aqui
    }
}

🧱 TypeScript Class Template

Prefixo: tsclass

Cria uma classe TypeScript simples com o mesmo nome do arquivo.

export default class NomeDoArquivo {
    // corpo da classe
}

🌐 Endpoint CRUD Template

Prefixo: endpoint

Cria um bloco de endpoints CRUD padrão, com placeholders automáticos para o nome da entidade e ID.

entity: {
    list: 'erp/v1/entity',
    create: 'erp/v1/entity',
    delete: (id: number) => `erp/v1/entity/${id}`,
    read: (id: number) => `erp/v1/entity/${id}`,
    update: (id: number) => `erp/v1/entity/${id}`,
},

🗺️ Paths CRUD Template

Prefixo: path

Cria um conjunto de rotas de navegação padrão (root, list, edit, editPath, create) para uso em paths.ts.

entity: {
    root: ROOTS.ENTITY,
    list: `${ROOTS.ENTITY}/list`,
    edit: (id: string) => `${ROOTS.ENTITY}/edit/${id}`,
    editPath: `${ROOTS.ENTITY}/edit/:id`,
    create: `${ROOTS.ENTITY}/new`,
},

📘 Zod Schema Template

Prefixo: zschema

Cria automaticamente um Zod Schema com base no nome do arquivo, junto com o tipo inferido.

import zod from 'src/utils/zod'

const NomeDoArquivo = zod.object({
    // campos aqui
})

type NomeDoArquivoType = zod.infer<typeof NomeDoArquivo>

export type { NomeDoArquivoType }

export { NomeDoArquivo }

💡 Dica

O nome ${TM_FILENAME_BASE} é substituído automaticamente pelo nome do arquivo atual.

Use ${1}, ${2} e outros placeholders para navegar rapidamente entre os pontos editáveis com Tab.