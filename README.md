# LinkedList
Delete even number of data of List


void Delete(LIST &l){
	NODE *k = NULL;
	while((l.pHead->data % 2) == 0){
		k = l.pHead;
		l.pHead = l.pHead->pNext;
		delete k;
		if (l.pHead == NULL) return;
	}
	NODE *p = l.pHead;
	NODE *g = p;
	while(p!= NULL){
		int index = 0;
		while (p!= NULL){
			if (p->data % 2 == 0) break;
			if (index >= 1 ) g = p;
			p = p->pNext;
			index++;
		}
	
		if ( p == NULL ) {
			return;
		}
		else if (p!=NULL){
			NODE* h = p;
			g->pNext = h->pNext;
			p = g->pNext;
			delete h;
		}
	}
}
