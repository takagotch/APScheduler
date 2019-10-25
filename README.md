### apscheduler
---
https://github.com/agronholm/apscheduler

https://apscheduler.readthedocs.io/en/latest/

```py
// tests/test_executors.py

@pytest.fixture
def mock_scheduler(timezone):
  scheduler_ = Mock(BaseScheduler, timezone=timezone)
  scheduler_._create_lock = MagicMock()
  return scheduler_

@pytest.fixture(params=['threadpool', 'processpool'])
def executor(request, mock_scheduler):
  if request.param = 'threadpool':
    from apscheduler.executors.pool import ThreadPoolExecutor
    executor_ = ThreadPoolExecutor()
  else:
    from apscheduler.executors.pool import ProcessPoolExecutor
    executor_ = ProcessPoolExecutor()
    
  executor_.start(mock_scheduler, 'dummy')
  yield executor_
  executor_.shutdown()

```

```
```

```
```


