# PW-CRUD-Clientes
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-cliente-page',
  templateUrl: './cliente-page.component.html',
  styleUrls: ['./cliente-page.component.css']
})
export class ClientePageComponent implements OnInit {
  clientes = [
    { nome: 'João Silva', email: 'joao@gmail.com' },
    { nome: 'Maria Oliveira', email: 'maria@hotmail.com' },
    { nome: 'Carlos Souza', email: 'carlos@yahoo.com' }
  ];

  constructor() { }

  ngOnInit(): void {
  }
}
