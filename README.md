# PW-CRUD-Clientes

<div class="cliente-container">
  <h2>Lista de Clientes</h2>

  <ul>
    <li *ngFor="let cliente of clientes; let i = index">
      <strong>{{ cliente.nome }}</strong> - {{ cliente.email }}
      <button (click)="editarCliente(i)">Editar</button>
      <button (click)="excluirCliente(i)">Excluir</button>
    </li>
  </ul>

  <h3>{{ editandoIndex !== null ? 'Editar Cliente' : 'Novo Cliente' }}</h3>

  <input type="text" [(ngModel)]="novoNome" placeholder="Nome">
  <input type="email" [(ngModel)]="novoEmail" placeholder="Email">

  <button *ngIf="editandoIndex === null" (click)="adicionarCliente()">Adicionar</button>
  <button *ngIf="editandoIndex !== null" (click)="salvarEdicao()">Salvar</button>
  <button *ngIf="editandoIndex !== null" (click)="cancelarEdicao()">Cancelar</button>
</div>
